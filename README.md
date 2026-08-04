# DeBounce (debounce)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

DeBounce is an email validation and verification REST API that helps developers ensure the deliverability and quality of email addresses at scale. The API supports real-time single email validation, asynchronous bulk list processing, and data enrichment via reverse email lookup. It detects disposable addresses, role-based emails, catch-all domains, syntax errors, and performs MX record and SMTP-level mailbox verification. DeBounce offers pay-as-you-go credit-based pricing with no monthly subscription required, full API access at every tier, and credits that never expire.

- **APIs.json**: https://raw.githubusercontent.com/api-evangelist/debounce/refs/heads/main/apis.yml
- **Naftiko**: https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=debounce-api-evangelist&utm_content=repo

## Tags

- Email Validation
- Email Verification
- Deliverability
- Disposable Email Detection
- MX Records
- Bulk Email Validation
- Data Enrichment
- Syntax Validation

## APIs

| Name | Description | Docs |
|------|-------------|------|
| DeBounce Email Validation API | Real-time and bulk email address verification, deliverability checks, disposable/role-based detection, MX record validation, SMTP verification, data enrichment, and disposable domain detection. | [Documentation](https://developers.debounce.com/) |

## Plans / Rate Limits / FinOps

| Resource | File |
|----------|------|
| Plans & Pricing | [plans/debounce-plans-pricing.yml](plans/debounce-plans-pricing.yml) |
| Rate Limits | [rate-limits/debounce-rate-limits.yml](rate-limits/debounce-rate-limits.yml) |
| FinOps | [finops/debounce-finops.yml](finops/debounce-finops.yml) |

**Pricing summary:** Pay-as-you-go credits from $0.002/email (5K pack) to $0.00035/email (5M pack). 100 free credits on signup. Credits never expire. No monthly subscription required.

**Rate limits summary:** Private API keys support 5 concurrent requests (2 with data enrichment enabled). Public keys limited to 20 validations per IP per day. One bulk validation job active per account at a time.

## Timestamps

| Field | Value |
|-------|-------|
| Created | 2026-06-12 |
| Modified | 2026-06-12 |

## Common

| Type | URL |
|------|-----|
| Website | https://debounce.com/ |
| Documentation | https://developers.debounce.com/ |
| GitHub Org | https://github.com/debounceio |
| LinkedIn | https://www.linkedin.com/company/debounceio |
| Blog | https://debounce.com/blog/ |
| Pricing | https://debounce.com/pricing/ |
| Status Page | https://status.debounce.com/ |
| X | https://x.com/debounceio |

## Maintainers

| Name | Email |
|------|-------|
| Kin Lane | kin@apievangelist.com |
