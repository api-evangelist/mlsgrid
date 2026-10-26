# mlsgrid (mlsgrid)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
