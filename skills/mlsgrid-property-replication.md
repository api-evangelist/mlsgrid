---
name: mlsgrid-property-replication
description: Replicate MLS Grid Property listings for one originating MLS - initial full load, then incremental catch-up on the ModificationTimestamp watermark.
api: mlsgrid Property API
operations:
  - listProperties
  - getProperty
  - listLookups
generated: '2026-09-17'
method: generated
source: openapi/mlsgrid-property-api-openapi.yml + https://docs.mlsgrid.com/api-documentation/api-version-2.0.md
---

# Replicate MLS Grid Property data

MLS Grid is a **replication** API, not a search API. It does not support real-time access. You pull
changes on a watermark and keep your own copy.

## Before you start

- You need a long-lived OAuth 2.0 bearer token from the token tab of your MLS Grid data
  subscription. It is issued only after the Master Data License Agreement is signed and the
  originating MLS has approved your licensee. There is no self-serve key and no sandbox.
- Send `Accept-Encoding: gzip` on **every** request. Compression is checked *before* authentication:
  a request without it returns `400 COMPRESSION REQUIRED`, not `401`.
- Every request must `$filter` on exactly **one** `OriginatingSystemName` (case sensitive, usually
  lowercase: `actris`, `mred`, `nwmls`, ...). One MLS per query.

## Step 1 - initial full load (`listProperties`)

`GET /Property` with a filter that includes `MlgCanView eq true`, so the first load carries only
records you are licensed to display:

```
GET /Property?$filter=OriginatingSystemName eq 'actris' and MlgCanView eq true&$top=1000&$expand=Media,Rooms,UnitTypes
Authorization: Bearer <token>
Accept-Encoding: gzip
```

Follow `@odata.nextLink` until the response no longer contains one. Save the greatest
`ModificationTimestamp` you have seen for this resource - that is your watermark.

Page-size ceilings: `$top` may be up to **5000** without `$expand` and **1000** with it. Ask for more
and the request errors.

## Step 2 - incremental replication (`listProperties`)

Drop the `MlgCanView` predicate. You now want deletions too:

```
GET /Property?$filter=OriginatingSystemName eq 'actris' and ModificationTimestamp gt 2026-09-17T00:00:00.00Z&$top=1000
```

For each record returned:

1. `MlgCanView` is `false` -> **delete** the record from your store. It disappears from the feed
   entirely after 7 days, so a missed pass loses the delete signal.
2. `MlgCanView` is `true` -> upsert the record.
3. `PhotosChangeTimestamp` changed -> the media set changed; re-read media (see
   `mlsgrid-media-download`).
4. Save the new greatest `ModificationTimestamp` **after** acting on the record, not before - a crash
   mid-batch must not advance the watermark past work you did not do.

Repeat on a schedule. MLS Grid re-imports each member MLS every minute where the MLS permits it.

## Step 3 - one record by key (`getProperty`)

`GET /Property('actris-1234567')`. Keys are prefixed with the originating MLS code so they stay
unique across pooled MLSs. Include the prefix when querying; strip it before displaying.

## Step 4 - enumerated values (`listLookups`)

Field values are per-MLS. `GET /Lookup?$filter=OriginatingSystemName eq 'actris'` enumerates them.
Replicate `Lookup` on the same watermark pattern - lookup renames are the most common breaking
change MLS Grid announces.

## Rules that will stop you

- **Rate limits:** 2 requests/second, 7,200/hour, 40,000/24h, 4 GB/hour. Exceeding any of them
  returns `429` **and suspends your access token**; it is reinstated automatically once usage falls
  back inside the limits, and the primary contact is emailed. Email support@mlsgrid.com *in advance*
  if you need more.
- **No `$select` or `$orderby` on `$expand`ed resources.**
- **At most 5 `or` operators** in a `$filter`; prefer the `in` operator (new in 2.0).
- **Errors** are the OData shape `{"error":{"code":401,"message":"..."}}`, not RFC 9457.
- **Retries are safe.** Every operation is a `GET`; there is no write surface and no idempotency key.
