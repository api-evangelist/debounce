# DeBounce

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

DeBounce is an email validation and verification REST API that helps developers ensure the deliverability and quality of email addresses at scale. The API supports real-time single email validation, asynchronous bulk list processing, and data enrichment via reverse email lookup. It detects disposable addresses, role-based emails, catch-all domains, syntax errors, and performs MX record and SMTP-level mailbox verification. DeBounce offers pay-as-you-go credit-based pricing with no monthly subscription required, full API access at every tier, and credits that never expire. The surface is split across four hosts — api.debounce.io for validation, enrichment and account operations, bulk.debounce.io for asynchronous list jobs, disposable.debounce.io for the free disposable detector, and logo.debounce.com for the free company logo lookup — and DeBounce publishes OpenAPI 3.1.0, llms.txt, an A2A agent card, an agent skill and a remote MCP server from its developer portal.

**Areas:** Email Verification · Deliverability · Disposable Email Detection · MX Records · Bulk Email Validation · Data Enrichment · Syntax Validation · Reverse Email Lookup · Logo API · A2A

## DeBounce on APIs.io

Everything profiled for DeBounce is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/debounce/](https://apis.io/providers/debounce/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [DeBounce Logo API](https://apis.io/apis/debounce/debounce-logo-api/) — Free company logo lookup service positioned as a drop-in replacement for the deprecated Clearbit Logo API. A GET against logo.debounce.com with a company…
- [DeBounce Account Management API](https://apis.io/apis/debounce/debounce-account-management-api/) — The Account Management API from DeBounce — 1 operation(s) for account management.
- [DeBounce Disposable Email Detector API](https://apis.io/apis/debounce/debounce-debounce-disposable-email-detector-api-api/) — The DeBounce Disposable Email Detector API API from DeBounce — 1 operation(s) for debounce disposable email detector api.
- [DeBounce Email Validation API](https://apis.io/apis/debounce/debounce-debounce-email-validation-api-api/) — The DeBounce Email Validation API API from DeBounce — 1 operation(s) for debounce email validation api.
- [DeBounce Reverse API](https://apis.io/apis/debounce/debounce-reverse-api/) — The Reverse API from DeBounce — 1 operation(s) for reverse.
- [DeBounce Status API](https://apis.io/apis/debounce/debounce-status-api/) — The Status API from DeBounce — 1 operation(s) for status.
- [DeBounce Upload API](https://apis.io/apis/debounce/debounce-upload-api/) — The Upload API from DeBounce — 1 operation(s) for upload.
- [DeBounce Usage API](https://apis.io/apis/debounce/debounce-usage-api/) — The Usage API from DeBounce — 1 operation(s) for usage.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [debounce-mcp.yml](https://apis.io/servers/debounce/debounce-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Debounce Agentic Access](https://apis.io/agentic-access/debounce/debounce-agentic-access/)

#### JSON Schema (1)

The data models the API reads and writes.

- [DeBounce Validation Result](https://apis.io/schemas/debounce/debounce-validation-result/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Debounce Context](https://apis.io/jsonld/debounce/debounce-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [DeBounce Email Validation API Vocabulary](https://apis.io/vocabularies/debounce/debounce-vocabulary/)

#### Examples (1)

Example requests and responses.

- [Debounce Single Validation Example](https://apis.io/examples/debounce/debounce-single-validation-example/)

#### Collections (9)

Postman and Open Collection request collections.

- [DeBounce Email Validation API — Account](https://apis.io/collections/debounce/open-debounce-account-api/)
- [DeBounce Bulk Email Validation API](https://apis.io/collections/debounce/open-debounce-bulk-api/)
- [DeBounce Email Validation API — Data Enrichment](https://apis.io/collections/debounce/open-debounce-data-api/)
- [DeBounce Disposable Email Detector API](https://apis.io/collections/debounce/open-debounce-disposable-api/)
- [DeBounce Email Validation API — Single Validation](https://apis.io/collections/debounce/open-debounce-validation-api/)
- [DeBounce Email Validation Account API](https://apis.io/collections/debounce/postman-debounce-account-api/)
- [DeBounce Email Validation Account Bulk API](https://apis.io/collections/debounce/postman-debounce-bulk-api/)
- [DeBounce Email Validation Account Data API](https://apis.io/collections/debounce/postman-debounce-data-api/)
- [DeBounce Email Account Validation API](https://apis.io/collections/debounce/postman-debounce-validation-api/)

#### Overlays (12)

OpenAPI overlays, including conversational phrasing for each operation.

- [Debounce Account Api Overlay](https://apis.io/overlays/debounce/debounce-account-api-overlay/)
- [Debounce Account Management Api Phrasing Overlay](https://apis.io/overlays/debounce/debounce-account-management-api-phrasing-overlay/)
- [Debounce Bulk Api Overlay](https://apis.io/overlays/debounce/debounce-bulk-api-overlay/)
- [Debounce Data Api Overlay](https://apis.io/overlays/debounce/debounce-data-api-overlay/)
- [Debounce Debounce Disposable Email Detector Api Api Phrasing Overlay](https://apis.io/overlays/debounce/debounce-debounce-disposable-email-detector-api-api-phrasing-overlay/)
- [Debounce Debounce Email Validation Api Api Phrasing Overlay](https://apis.io/overlays/debounce/debounce-debounce-email-validation-api-api-phrasing-overlay/)
- [Debounce Disposable Api Overlay](https://apis.io/overlays/debounce/debounce-disposable-api-overlay/)
- [Debounce Reverse Api Phrasing Overlay](https://apis.io/overlays/debounce/debounce-reverse-api-phrasing-overlay/)
- [Debounce Status Api Phrasing Overlay](https://apis.io/overlays/debounce/debounce-status-api-phrasing-overlay/)
- [Debounce Upload Api Phrasing Overlay](https://apis.io/overlays/debounce/debounce-upload-api-phrasing-overlay/)
- [Debounce Usage Api Phrasing Overlay](https://apis.io/overlays/debounce/debounce-usage-api-phrasing-overlay/)
- [Debounce Validation Api Overlay](https://apis.io/overlays/debounce/debounce-validation-api-overlay/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [DeBounce — jsonschema rules](https://apis.io/rules/debounce/debounce-jsonschema-spectral-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Debounce Authentication](https://apis.io/security/debounce/debounce-authentication/)
- [Debounce Domain Security](https://apis.io/security/debounce/debounce-domain-security/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Debounce Scopes](https://apis.io/scopes/debounce/debounce-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Debounce Plans Pricing](https://apis.io/plans/debounce/debounce-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Debounce Rate Limits](https://apis.io/rate-limits/debounce/debounce-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Debounce Finops](https://apis.io/finops/debounce/debounce-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://debounce.com/)
- [Documentation](https://developers.debounce.com/)
- [Getting started](https://developers.debounce.com/)
- [API reference](https://developers.debounce.com/api-reference/endpoint/single-validation)
- [Pricing](https://debounce.com/pricing/)
- [Sign up](https://app.debounce.com/register)
- [Support](https://help.debounce.com/)
- [Changelog](https://feedback.debounce.com/changelog)
- [Blog](https://debounce.com/blog/)
- [Compliance](https://debounce.com/gdpr/)
- [Terms of service](https://debounce.com/terms-of-use/)
- [Privacy policy](https://debounce.com/privacy-policy/)
- [GitHub](https://github.com/debounceio)
- [Status](https://status.debounce.com/)

## API Evangelist rating

**Kin Score 68.8** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 80.0 |
| Contract quality | 53.8 |
| Contract governance | 41.7 |
| Operational transparency | 63.2 |
| Developer ergonomics | 68.6 |
| Access clarity | 84.2 |

**Agent readiness 60.8** — agent-native

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | platform (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | na |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 39.2** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/debounce/](https://apis.io/providers/debounce/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for DeBounce: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/debounce/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
