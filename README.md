# MLS Grid (mlsgrid)
The MLS Grid is a normalized, RESO Data Dictionary compliant data distribution platform that gives brokers, MLSs, and application vendors a single OData v4 Web API and one master data license agreement covering 50+ participating MLSs across the United States. The MLS Grid Web API standardizes Property, Member, Office, OpenHouse, Media, and Lookup resources for IDX, VOW, broker-only, and product-testing use cases, replacing the per-MLS RETS feed sprawl that historically burdened real-estate technology vendors.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/mlsgrid/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- Real Estate, MLS, RESO, OData, Property, Replication

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Tier

Tier 1 — Standards-aligned (RESO Data Dictionary + RESO Web API), documented rate limits, normalized multi-MLS surface, replication-optimized. See [review.yml](review.yml).

## APIs

### MLS Grid RESO Web API

Normalized, RESO-compliant OData v4 Web API for incremental replication of MLS listing data — Property, Member, Office, OpenHouse, Media, and Lookup. Authenticated with long-lived OAuth 2.0 bearer tokens. Optimized for bulk replication via `$filter` on `OriginatingSystemName` and `ModificationTimestamp`, with `$expand` of Media, Rooms, and UnitTypes inline on Property.

**Base URL:** `https://api.mlsgrid.com/v2/`

**Human URL:** [https://docs.mlsgrid.com/api-documentation/api-version-2.0.md](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)

- [Documentation — Master](https://docs.mlsgrid.com/master.md)
- [Documentation — API v2.0](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)
- [OData $metadata](https://api.mlsgrid.com/v2/$metadata)
- [OpenAPI](openapi/mlsgrid-reso-web-api-openapi.yml)
- [JSON Schema — Property](json-schema/mlsgrid-property-schema.json)
- [JSON Schema — Media](json-schema/mlsgrid-media-schema.json)
- [JSON-LD](json-ld/mlsgrid-context.jsonld)
- [Naftiko Capability — Property Replication](capabilities/property-replication.yaml)
- [Naftiko Capability — Member Replication](capabilities/member-replication.yaml)
- [Naftiko Capability — Office Replication](capabilities/office-replication.yaml)
- [Naftiko Capability — OpenHouse Replication](capabilities/openhouse-replication.yaml)
- [Naftiko Capability — Media Replication](capabilities/media-replication.yaml)
- [Naftiko Capability — Lookup Replication](capabilities/lookup-replication.yaml)

## Common Properties

- [Portal — mlsgrid.com](https://www.mlsgrid.com)
- [Documentation — docs.mlsgrid.com](https://docs.mlsgrid.com)
- [Documentation — Sitemap](https://docs.mlsgrid.com/sitemap.md)
- [Documentation — RESO Data Dictionary](https://www.reso.org/data-dictionary/)
- [Documentation — RESO Web API Specification](https://www.reso.org/reso-web-api/)
- [GitHubOrganization](https://github.com/mlsgrid)
- [Support — support@mlsgrid.com](mailto:support@mlsgrid.com)
- [Contact — info@mlsgrid.com](mailto:info@mlsgrid.com)

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [MLS Grid RESO Web API](openapi/mlsgrid-reso-web-api-openapi.yml)

### JSON Schema

- [Property](json-schema/mlsgrid-property-schema.json)
- [Media](json-schema/mlsgrid-media-schema.json)

### JSON-LD

- [MLS Grid Context](json-ld/mlsgrid-context.jsonld)

### Capabilities (Naftiko)

- [Property Replication](capabilities/property-replication.yaml)
- [Member Replication](capabilities/member-replication.yaml)
- [Office Replication](capabilities/office-replication.yaml)
- [OpenHouse Replication](capabilities/openhouse-replication.yaml)
- [Media Replication](capabilities/media-replication.yaml)
- [Lookup Replication](capabilities/lookup-replication.yaml)

### Vocabulary

- [MLS Grid Vocabulary](vocabulary/mlsgrid-vocabulary.yml)

### Spectral Rules

- [MLS Grid Ruleset](rules/mlsgrid-rules.yml)

### Examples

- [List Properties](examples/mlsgrid-list-properties-example.json)

### Commercial artifacts

- [Plans / Pricing](plans/mlsgrid-plans-pricing.yml)
- [Rate Limits](rate-limits/mlsgrid-rate-limits.yml)
- [FinOps Definition](finops/mlsgrid-finops.yml)

### Review

- [Provider Review](review.yml)

## Replication Pattern

All MLS Grid replication clients follow the same loop:

1. Filter every collection by `OriginatingSystemName eq '<mls>'` and `ModificationTimestamp gt <watermark>`.
2. Expand related resources where needed: `$expand=Media,Rooms,UnitTypes` on Property.
3. Page through `@odata.nextLink` until exhausted.
4. Persist the latest seen `ModificationTimestamp` as the new watermark.
5. Honor `MlgCanView=false` by retaining records but suppressing display.
6. Honor `MlgCanUse` to gate IDX, VOW, BO, and PT surfaces.
7. Download `MediaURL` payloads locally; never hot-link.

## Rate Limits

| Scope | Limit |
|---|---|
| Requests / second | 2 |
| Requests / hour | 7,200 |
| Requests / 24h | 40,000 |
| Download volume / hour | 4 GB |

Violations return HTTP 429 with suspension details; repeat offenders may have their token suspended. Exceptions are negotiated via `support@mlsgrid.com`.

## Maintainers

**FN:** Kin Lane

**Email:** info@apievangelist.com
