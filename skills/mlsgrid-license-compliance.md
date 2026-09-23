---
name: mlsgrid-license-compliance
description: Honor the MLS Grid Master Data License Agreement in code - MlgCanView deletion handling, MlgCanUse display gating for IDX/VOW/BO/PT, and the quarterly compliance audit.
api: mlsgrid Property API
operations:
  - listProperties
  - listMembers
  - listOffices
  - listOpenHouses
generated: '2026-09-17'
method: generated
source: openapi/ + https://docs.mlsgrid.com/api-documentation/api-version-2.0.md
---

# Stay inside the MLS Grid license

MLS Grid's whole product is *one* license agreement across 50+ MLSs. The obligations arrive in the
payload, on every resource, as two `Mlg`-prefixed fields. Any field prefixed `Mlg` is MLS Grid's own,
not RESO Data Dictionary.

## `MlgCanView` - the delete signal

Boolean. `false` means the record is no longer valid for your feed type and **must be removed from
your data store**. Records flagged `false` leave the feed entirely after **7 days**, so a replication
pass that skips a week loses the instruction permanently.

This is why the incremental query must *not* filter on `MlgCanView eq true` - filtering it out hides
your own deletions. Filter on it for the initial load only.

## `MlgCanUse` - the display gate

An array of the use cases the record qualifies for under the Master Data License Agreement:

| Value | Meaning |
|---|---|
| `IDX` | Public consumer display |
| `VOW` | Authenticated consumer display |
| `BO` | Back office |
| `PT` | Broker only / participant data access |

Check `MlgCanUse` against the surface you are about to render on. A record licensed for `VOW` only
must not appear on a public page. Apply the check at render time, per record - it is per record, not
per feed.

## Identifier hygiene

- Keys and MlsIds are prefixed with the originating MLS code (`actris-1234567`). Query with the
  prefix; strip it before showing an identifier to a consumer.
- MLS-specific (non-Data-Dictionary) fields carry a four-character prefix and an underscore -
  `ACT_ActiveOpenHouseCount`, `MRD_`, `NWM_`. Do not assume they exist on another MLS.
- All Data-Dictionary date fields are UTC regardless of source MLS; unconverted local date fields
  are not.

## What MLS Grid checks

MLS Grid runs **quarterly compliance audits** of the websites displaying licensed listings, on
behalf of the participating MLSs. The things that fail an audit are the ones above: displaying a
record after `MlgCanView` went false, displaying it on a surface its `MlgCanUse` does not cover, and
hotlinking `MediaURL` instead of storing a local copy.
