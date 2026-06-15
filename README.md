# mlsgrid (mlsgrid)

The MLS Grid is a normalized, RESO-compliant data distribution platform that gives brokers, MLSs, and application vendors a single OData v4 Web API and one master data license agreement covering 50+ participating MLSs across the United States. Built on the RESO Data Dictionary, the MLS Grid Web API standardizes Property, Member, Office, OpenHouse, Media, and Lookup resources for IDX, VOW, broker-only, and product-development use cases, replacing the per-MLS RETS feed sprawl that historically burdened real-estate technology vendors.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/mlsgrid/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/mlsgrid/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming

## Timestamps

- **Created:** 2026-05-25T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### MLS Grid RESO Web API

Normalized, RESO Data Dictionary–compliant OData v4 Web API for incremental replication of MLS listing data — Property, Member, Office, OpenHouse, Media, and Lookup resources — across the participating MLS Grid boards. Authenticated with long-lived OAuth 2.0 bearer tokens. Optimized for bulk replication via $filter on OriginatingSystemName and ModificationTimestamp with $expand of Media, Rooms, and UnitTypes.

- **Human URL:** [https://docs.mlsgrid.com/api-documentation/api-version-2.0.md](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)
- **Base URL:** `https://api.mlsgrid.com/v2/`

#### Tags

- Real Estate
- MLS
- RESO
- OData
- Property
- Replication

#### Properties

- [Documentation](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)
- [Documentation](https://docs.mlsgrid.com/master.md)
- [Metadata](https://api.mlsgrid.com/v2/$metadata)
- [OpenAPI](openapi/mlsgrid-reso-web-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/mlsgrid-reso-web-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/mlsgrid-reso-web-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/mlsgrid-property-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/mlsgrid-media-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/mlsgrid-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

## Common Properties

- [Portal](https://www.mlsgrid.com)
- [Documentation](https://docs.mlsgrid.com)
- [Documentation](https://docs.mlsgrid.com/master.md)
- [Documentation](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)
- [Documentation](https://docs.mlsgrid.com/sitemap.md)
- [Resources](https://www.mlsgrid.com)
- [Privacy Policy](https://www.mlsgrid.com)
- [Terms of Service](https://www.mlsgrid.com)
- [Support](mailto:support@mlsgrid.com)
- [Contact](mailto:info@mlsgrid.com)
- [GitHub Organization](https://github.com/mlsgrid)
- [Documentation](https://www.reso.org/data-dictionary/)
- [Documentation](https://www.reso.org/reso-web-api/)
- [Plans](plans/mlsgrid-plans-pricing.yml)
- [Rate Limits](rate-limits/mlsgrid-rate-limits.yml)
- [Fin Ops](finops/mlsgrid-finops.yml)
- [Vocabulary](vocabulary/mlsgrid-vocabulary.yml)
- [Spectral Ruleset](rules/mlsgrid-rules.yml)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
