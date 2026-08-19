---
name: De Bounce
description: Use when validating email addresses, processing bulk email lists, enriching contact data with names and avatars, or monitoring account usage and credit balance. Reach for this skill when building signup flows, CRM integrations, email verification workflows, or any application requiring email quality checks.
metadata:
    mintlify-proj: debounce
    version: "1.0"
---

# DeBounce API Skill

## Product summary

DeBounce is a REST API for email validation, verification, and enrichment at scale. It validates single emails, processes bulk lists asynchronously, enriches contact data with names and avatars, and provides usage monitoring. The API uses a simple query-string authentication model with a 13-character alphanumeric API key. Primary endpoint: `https://api.debounce.io/v1/`. All requests require the `api=YOUR_API_KEY` parameter. Responses return JSON with a `success` field (1 or 0) and data nested in a `debounce` object. See the full documentation at https://developers.debounce.com.

## When to use

Reach for this skill when:
- **Validating single emails** in signup forms, login flows, or contact submissions
- **Processing bulk email lists** (up to 200,000 emails per file) asynchronously
- **Enriching contact records** with full names and profile photos
- **Checking email quality** before sending transactional or marketing emails
- **Monitoring account usage** and remaining credit balance programmatically
- **Detecting disposable or risky emails** to prevent spam signups
- **Building real-time form validation** with client-side public API keys

Do not use this skill for: authentication/authorization, user account management, or operations outside the email validation domain.

## Quick reference

### API Endpoints

| Endpoint | Method | Purpose |
|----------|--------|---------|
| `/v1/` | GET | Validate single email with optional enrichment |
| `/v1/upload/` | GET | Upload bulk email list for async validation |
| `/v1/status/` | GET | Check bulk validation progress and download results |
| `/v1/balance/` | GET | Retrieve remaining credit balance |
| `/v1/usage/` | GET | Get daily usage statistics within date range |

### Authentication

- **API Key Format**: 13-character alphanumeric token (e.g., `abc123def456g`)
- **How to Pass**: Append `&api=YOUR_API_KEY` to query string
- **Where to Get**: Log in to DeBounce dashboard → API Settings page
- **Security**: Store securely; never expose in client-side code or public repos

### Single Email Validation Parameters

| Parameter | Type | Purpose | Cost |
|-----------|------|---------|------|
| `email` | string | Email address to validate | Base (1 credit) |
| `photo` | boolean | Include profile photo if available | +1 credit per success |
| `append` | boolean | Include full name and avatar | +20 credits per success |
| `gsuite` | boolean | Detect G Suite accept-all emails | Included |

### Response Fields (Single Validation)

| Field | Type | Values | Meaning |
|-------|------|--------|---------|
| `result` | string | Safe to Send, Invalid, Disposable, Accept-all, Unknown | Overall validation status |
| `reason` | string | Deliverable, Invalid, Risky, etc. | Detailed reason |
| `code` | integer | 1-5 | Numeric result code |
| `send_transactional` | integer | 0 or 1 | Safe for transactional email (1 = yes) |
| `role` | boolean | true/false | Is this a role account (info@, support@, etc.) |
| `free_email` | boolean | true/false | Is this a free email provider (Gmail, Yahoo, etc.) |
| `did_you_mean` | string | Email address or empty | Suggested correction if typo detected |
| `balance` | integer | Remaining credits | Credits left on account |

### Bulk Upload File Requirements

- **Format**: `.csv` or `.txt`
- **Size**: Less than 20MB
- **Max Emails**: 200,000 per file
- **Structure**: One email per line
- **Hosting**: Must be on your own server with public HTTPS URL (not Google Drive, Dropbox, OneDrive)
- **Concurrency**: Only one active bulk job per account; additional uploads are queued

### HTTP Status Codes

| Code | Meaning | Action |
|------|---------|--------|
| 200 | Success | Process response normally |
| 401 | Unauthorized | Check API key validity and format |
| 402 | Payment Required | Add credits to account |
| 403 | Forbidden | Verify API key permissions |
| 429 | Too Many Requests | Reduce concurrency or wait; see rate limits |

### Rate Limits

**Private API Key (Server-Side)**:
- 5 concurrent requests max (2 if enrichment enabled)
- Returns HTTP 429 if exceeded

**Public API Key (Client-Side)**:
- 20 validations per IP per day
- Returns HTTP 429 if exceeded

**Bulk Validation**:
- One active job per account
- Additional uploads queued automatically

## Decision guidance

### When to use single validation vs bulk upload

| Scenario | Use Single Validation | Use Bulk Upload |
|----------|----------------------|-----------------|
| Real-time form validation | ✓ | |
| Signup flow (1-10 emails) | ✓ | |
| Validating 100+ emails | | ✓ |
| Async processing acceptable | | ✓ |
| Immediate response required | ✓ | |
| Large email list cleanup | | ✓ |
| CRM contact enrichment | ✓ (with append) | ✓ (with append) |

### When to enable enrichment options

| Need | Parameter | Cost | Use When |
|------|-----------|------|----------|
| Profile photo only | `photo=true` | +1 credit | Building user profiles, avatars |
| Full name + avatar | `append=true` | +20 credits | CRM enrichment, contact records |
| Neither | Omit both | Base cost | Budget-conscious, validation only |

### When to treat emails as valid in signup forms

Use these statuses as acceptable for new user registration:
- **Deliverable** (safe to send)
- **Accept-all** (domain accepts all addresses)
- **Unknown** (cannot verify but not risky)

Check `send_transactional = 1` as a shortcut: if true, email is acceptable for signup.

## Workflow

### Validate a single email

1. **Construct the request**: Build URL with `email` parameter and your API key
   ```
   https://api.debounce.io/v1/?email=user@example.com&api=YOUR_API_KEY
   ```

2. **Add optional parameters** if needed:
   - `&photo=true` for profile photo
   - `&append=true` for full name and avatar
   - `&gsuite=true` to detect G Suite accept-all

3. **Send GET request** and parse JSON response

4. **Check `success` field**: If `"1"`, process `debounce` object; if `"0"`, handle error in `debounce.error`

5. **For signup forms**: Accept if `result` is "Safe to Send", "Accept-all", or "Unknown", OR if `send_transactional = 1`

6. **Monitor balance**: Track `balance` field to avoid running out of credits

### Process a bulk email list

1. **Prepare file**: Create `.csv` or `.txt` with one email per line; keep under 20MB and 200,000 emails

2. **Host file**: Upload to your own server with public HTTPS URL ending in `.csv` or `.txt`

3. **Upload list**: Send GET request to `/v1/upload/` with `file_url` parameter
   ```
   https://api.debounce.io/v1/upload/?file_url=https://yourserver.com/emails.csv&api=YOUR_API_KEY
   ```

4. **Check response**: Confirm `success = "1"` and note the job ID returned

5. **Poll for status**: Call `/v1/status/` endpoint periodically to check progress
   ```
   https://api.debounce.io/v1/status/?api=YOUR_API_KEY
   ```

6. **Download results**: When status shows "completed", response includes `.csv` download link

7. **Handle queuing**: If another job is running, your upload is queued; check status to see when it starts

### Enrich contact data

1. **For full name + avatar**: Add `&append=true` to single validation request (costs 20 credits per success)

2. **For photo only**: Add `&photo=true` (costs 1 credit per success)

3. **Parse response**: Enriched data returned in `debounce` object alongside validation result

4. **Budget credits**: Plan for 20-credit cost per enrichment; check balance before bulk enrichment

### Monitor usage and balance

1. **Check balance**: Every API response includes `balance` field showing remaining credits

2. **Get usage stats**: Call `/v1/usage/` with date range (format: `YY-MM-DD`)
   ```
   https://api.debounce.io/v1/usage/?start=24-01-01&end=24-01-31&api=YOUR_API_KEY
   ```

3. **Track spending**: Use usage endpoint to understand daily consumption patterns

4. **Prevent overages**: Set alerts when balance drops below threshold; add credits before hitting zero

## Common gotchas

- **Missing API key**: Every request requires `&api=YOUR_API_KEY` in query string; requests without it return 401 Unauthorized. Do not forget this parameter.

- **Exhausted credits**: When balance reaches zero, API returns 402 Payment Required. Add credits immediately; there is no grace period.

- **Bulk file hosting**: Files must be on your own server with public HTTPS URL. Google Drive, Dropbox, OneDrive links are rejected. Test the URL in a browser first to confirm it's publicly accessible.

- **Bulk job queueing**: Only one bulk job runs at a time per account. If you upload while another job is processing, your upload is queued. Check status endpoint to see when it starts; do not re-upload the same file.

- **Concurrency limits**: Sending more than 5 concurrent requests (or 2 with enrichment) returns 429 Too Many Requests. Use a queue or connection pool to control concurrency.

- **Signup form validation**: Do not reject "Accept-all" or "Unknown" emails in signup flows; these are legitimate users. Use `send_transactional = 1` as a safe shortcut.

- **Enrichment cost**: `append=true` costs 20 credits per successful enrichment, not per request. Failed enrichments do not charge. Budget accordingly for bulk enrichment.

- **Date format in usage endpoint**: Use `YY-MM-DD` format (two digits for year, month, day). Earliest allowed start date is `20-08-14`. End date cannot be later than today.

- **Public API key limits**: Client-side public keys are limited to 20 validations per IP per day. This is per-IP, not per-user; shared networks (offices, schools) hit limits faster.

- **Response structure**: All responses nest data in a `debounce` object. Do not expect top-level fields; always access `debounce.email`, `debounce.result`, etc.

## Verification checklist

Before submitting work with DeBounce API:

- [ ] API key is valid and stored securely (not in client-side code or public repos)
- [ ] All requests include `&api=YOUR_API_KEY` parameter
- [ ] Single validation requests check `success = "1"` before processing response
- [ ] Signup forms accept "Deliverable", "Accept-all", and "Unknown" statuses (or check `send_transactional = 1`)
- [ ] Bulk uploads use files hosted on your own server with public HTTPS URL (not cloud storage)
- [ ] Bulk files are `.csv` or `.txt`, under 20MB, with max 200,000 emails
- [ ] Concurrency is controlled (max 5 concurrent requests, or 2 with enrichment)
- [ ] Enrichment costs (20 credits per `append=true`, 1 per `photo=true`) are budgeted
- [ ] Error handling covers 401 (bad key), 402 (no credits), 429 (rate limit)
- [ ] Balance is monitored to prevent running out of credits mid-workflow
- [ ] Bulk status is polled periodically; results are downloaded when complete
- [ ] Date format in usage endpoint is `YY-MM-DD` with valid date range

## Resources

- **Comprehensive navigation**: https://developers.debounce.com/llms.txt
- **API Reference**: https://developers.debounce.com/api-reference/endpoint/single-validation
- **Authentication Guide**: https://developers.debounce.com/api-concepts/authentication
- **Rate Limiting & Concurrency**: https://developers.debounce.com/api-concepts/rate-limiting

---

> For additional documentation and navigation, see: https://developers.debounce.com/llms.txt