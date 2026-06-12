# DeBounce (debounce)

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
