# Mlsgrid

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

**Areas:** Real Estate · Property Listings · MLS · RESO · Data Replication · OData · Housing · Data Licensing · IDX · Property Data

## Mlsgrid on APIs.io

Everything profiled for Mlsgrid is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/mlsgrid/](https://apis.io/providers/mlsgrid/)** — or go straight to one of the APIs or properties below.

### APIs (7)

- [mlsgrid Lookup API](https://apis.io/apis/mlsgrid/mlsgrid-lookup-api/) — Enumerated lookup values per originating MLS.
- [mlsgrid Media API](https://apis.io/apis/mlsgrid/mlsgrid-media-api/) — Listing media (photos, virtual tours) expanded from Property.
- [mlsgrid Member API](https://apis.io/apis/mlsgrid/mlsgrid-member-api/) — Real estate agents (RESO Data Dictionary Member resource).
- [mlsgrid Metadata API](https://apis.io/apis/mlsgrid/mlsgrid-metadata-api/) — OData service and EDMX metadata.
- [mlsgrid Office API](https://apis.io/apis/mlsgrid/mlsgrid-office-api/) — Brokerage offices (RESO Data Dictionary Office resource).
- [mlsgrid OpenHouse API](https://apis.io/apis/mlsgrid/mlsgrid-openhouse-api/) — Open house events (RESO Data Dictionary OpenHouse resource).
- [mlsgrid Property API](https://apis.io/apis/mlsgrid/mlsgrid-property-api/) — Property listings (RESO Data Dictionary Property resource).

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [mlsgrid-mcp.yml](https://apis.io/servers/mlsgrid/mlsgrid-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Mlsgrid Agentic Access](https://apis.io/agentic-access/mlsgrid/mlsgrid-agentic-access/)

#### JSON Schema (2)

The data models the API reads and writes.

- [MLS Grid Media](https://apis.io/schemas/mlsgrid/mlsgrid-media/)
- [MLS Grid Property](https://apis.io/schemas/mlsgrid/mlsgrid-property/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Mlsgrid Context](https://apis.io/jsonld/mlsgrid/mlsgrid-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [MLS Grid Vocabulary](https://apis.io/vocabularies/mlsgrid/mlsgrid-vocabulary/)

#### Examples (1)

Example requests and responses.

- [Mlsgrid List Properties Example](https://apis.io/examples/mlsgrid/mlsgrid-list-properties-example/)

#### Collections (8)

Postman and Open Collection request collections.

- [MLS Grid RESO Web Lookup API](https://apis.io/collections/mlsgrid/open-mlsgrid-lookup-api/)
- [MLS Grid RESO Web Lookup Media API](https://apis.io/collections/mlsgrid/open-mlsgrid-media-api/)
- [MLS Grid RESO Web Lookup Member API](https://apis.io/collections/mlsgrid/open-mlsgrid-member-api/)
- [MLS Grid RESO Web Lookup Metadata API](https://apis.io/collections/mlsgrid/open-mlsgrid-metadata-api/)
- [MLS Grid RESO Web Lookup Office API](https://apis.io/collections/mlsgrid/open-mlsgrid-office-api/)
- [MLS Grid RESO Web Lookup OpenHouse API](https://apis.io/collections/mlsgrid/open-mlsgrid-openhouse-api/)
- [MLS Grid RESO Web Lookup Property API](https://apis.io/collections/mlsgrid/open-mlsgrid-property-api/)
- [MLS Grid RESO Web API](https://apis.io/collections/mlsgrid/open-mlsgrid-reso-web-api/)

#### Overlays (7)

OpenAPI overlays, including conversational phrasing for each operation.

- [Mlsgrid Lookup Api Overlay](https://apis.io/overlays/mlsgrid/mlsgrid-lookup-api-overlay/)
- [Mlsgrid Media Api Overlay](https://apis.io/overlays/mlsgrid/mlsgrid-media-api-overlay/)
- [Mlsgrid Member Api Overlay](https://apis.io/overlays/mlsgrid/mlsgrid-member-api-overlay/)
- [Mlsgrid Metadata Api Overlay](https://apis.io/overlays/mlsgrid/mlsgrid-metadata-api-overlay/)
- [Mlsgrid Office Api Overlay](https://apis.io/overlays/mlsgrid/mlsgrid-office-api-overlay/)
- [Mlsgrid Openhouse Api Overlay](https://apis.io/overlays/mlsgrid/mlsgrid-openhouse-api-overlay/)
- [Mlsgrid Property Api Overlay](https://apis.io/overlays/mlsgrid/mlsgrid-property-api-overlay/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Mlsgrid — jsonschema rules](https://apis.io/rules/mlsgrid/mlsgrid-jsonschema-spectral-rules/)
- [Mlsgrid API Rules](https://apis.io/rules/mlsgrid/mlsgrid-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Mlsgrid Authentication](https://apis.io/security/mlsgrid/mlsgrid-authentication/)
- [Mlsgrid Domain Security](https://apis.io/security/mlsgrid/mlsgrid-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Mlsgrid Plans Pricing](https://apis.io/plans/mlsgrid/mlsgrid-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Mlsgrid Rate Limits](https://apis.io/rate-limits/mlsgrid/mlsgrid-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Mlsgrid Finops](https://apis.io/finops/mlsgrid/mlsgrid-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.mlsgrid.com/)
- [Documentation](https://docs.mlsgrid.com)
- [Getting started](https://docs.mlsgrid.com/data-consumer-guides/how-to-register-and-activate-an-mls-grid-data-consumer-account.md)
- [API reference](https://docs.mlsgrid.com/api-documentation/api-version-2.0.md)
- [Pricing](https://www.mlsgrid.com/interest-form)
- [Sign up](https://www.mlsgrid.com/interest-form)
- [Support](https://www.mlsgrid.com/contact-us)
- [Changelog](https://docs.mlsgrid.com/)
- [Blog](https://www.mlsgrid.com/news)
- [Compliance](https://certification.reso.org/summary/T00000045)
- [Terms of service](https://app.mlsgrid.com/termsofuse)
- [Privacy policy](https://app.mlsgrid.com/privacypolicy)
- [GitHub](https://github.com/mlsgrid)

## API Evangelist rating

**Kin Score 63.0** — strong · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 68.1 |
| Contract governance | 45.5 |
| Operational transparency | 52.6 |
| Developer ergonomics | 58.9 |
| Access clarity | 65.8 |

**Agent readiness 33.3** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | na |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | verified |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 24.5** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/mlsgrid/](https://apis.io/providers/mlsgrid/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Mlsgrid: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/mlsgrid/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
