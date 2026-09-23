---
name: mlsgrid-media-download
description: Retrieve and store MLS Grid listing media under the signed, single-use, one-hour URL regime that replaced the AWS S3/CloudFront delivery path on 2026-09-08.
api: mlsgrid Media API
operations:
  - listMedia
  - listProperties
generated: '2026-09-17'
method: generated
source: openapi/mlsgrid-media-api-openapi.yml + https://docs.mlsgrid.com/releases/upcoming-changes-to-media-delivery-migration-away-from-amazon-aws.md
---

# Download MLS Grid media

Media is the part of MLS Grid most likely to break an integration, and it changed twice in 2026.

## Where media comes from

Two shapes, depending on what the originating MLS permits:

- **Expanded**: `GET /Property?$expand=Media` (`listProperties`) returns media inline with the
  listing. Using `$expand` drops your page ceiling from 5000 to 1000.
- **Standalone**: `GET /Media` (`listMedia`) where the MLS exposes the resource on its own (for
  example Northstar MLS). Same `OriginatingSystemName` + `ModificationTimestamp` replication pattern.

## The 2026-09-08 delivery change

From **2026-09-08** MLS Grid serves media from `media.mlsgrid.com`, not from Amazon AWS. The URLs in
`MediaURL` are now:

- **Signed** - `token`, `expires` and `id` are cryptographically bound to the URL. Any reformatting,
  re-encoding or edit invalidates it.
- **Single-use** - you may download a given media item **once** in the hour after you retrieve its
  URL. A second download, or re-requesting a fresh URL for the same media inside that hour, returns
  `429`.
- **Time-limited** - the URL expires one hour after it is generated.

Two delivery methods were withdrawn: **S3 bucket-to-bucket transfer** is gone, and **CloudFront**
access must be repointed at the MLS Grid-operated CDN (contact support@mlsgrid.com). MLS Grid will
also provision CDN access that is *not* single-use/one-hour on request.

## The workflow that works

1. Read the record (expanded or standalone) and take `MediaURL` fresh.
2. Download **immediately**. Do not persist the URL for later, do not share it between workers, do
   not retry an already-used URL.
3. Store the bytes in your own storage. **Hotlinking `MediaURL` into a website or app is
   prohibited** by the license agreement.
4. Send a `User-Agent` header equal to your OAuth 2.0 access token on the media download - enforced
   since 2026-06-01; any other User-Agent may be denied.

## Knowing when to re-download

- `PhotosChangeTimestamp` (on Property, Member, Office) changed -> the media *set* changed; replace
  your local media records for that listing.
- `MediaModificationTimestamp` (on the media sub-document) changed -> that *image file* changed;
  re-download it.

Otherwise: media is immutable and keeps its identity. A given image never needs downloading twice -
which is what makes the single-use rule survivable.
