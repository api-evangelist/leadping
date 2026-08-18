---
name: leadping-lead-intake
description: Submit an external lead into a Leadping organization using an approved source key, and confirm it landed.
api: Leadping API
base_url: https://api.leadping.ai
generated: '2026-08-18'
method: generated
source: openapi/leadping-openapi.json + https://leadping.ai/docs/sending-leads-to-leadping
operations:
  - Leads_CreateExternal
  - Leads_CreateIntake
  - Leads_CreateIntakeFromQuery
  - Sources_Get
  - Sources_GetMetrics
  - Leads_GetForCurrentUser
---

# Submit a lead to Leadping

Use this when a form, publisher, partner, or posting system needs to hand a new lead to a Leadping
organization. This is the only Leadping flow that uses a source key.

## Credential

Send `Authorization: Bearer lp_src_...` — the approved **source key** for the source you are posting as.
This credential is accepted on exactly three operations and is rejected everywhere else:

| operationId | Call |
|---|---|
| `Leads_CreateExternal` | `POST /leads` |
| `Leads_CreateIntake` | `POST /leads/intake` |
| `Leads_CreateIntakeFromQuery` | `GET /leads/intake` |

Do not reach for an organization API key (`sk_...`) here, and never send a source key to any other
endpoint — Leadping rejects it and repeated invalid traffic can trigger source review.

## Steps

1. **Post the lead.** Call `Leads_CreateIntake` (`POST /leads/intake`) with the intake payload.
   `Leads_CreateIntakeFromQuery` exists for posting systems that can only emit a query string.
2. **Carry stable external identifiers.** `LeadIntakeRequest` accepts `externalId`, `sellerLeadId`,
   `subId` and `pubId`. Populate them. There is **no idempotency key on lead intake** — these fields are
   the only way your team can trace duplicates and reconcile with the posting system afterwards.
3. **Attach consent evidence.** Sources configured to require TrustedForm will reject leads that arrive
   without it. Confirm the source's requirement with `Sources_Get` before going live.
4. **Read the response.** A success returns the created lead. Resolve it later with
   `Leads_GetForCurrentUser` (`GET /leads/{id}`) using an organization credential.
5. **Watch source health.** `Sources_GetMetrics` (`GET /sources/{id}/metrics`) reports lead metrics for
   the source — use it to spot a posting integration that has started failing.

## Error handling

Errors are RFC 9457 Problem Details (`type`, `title`, `status`, `detail`, `instance`).

- `400` — the request was invalid or failed validation. **Do not retry unchanged.** Repeating an invalid
  request can trigger source review or throttling.
- `401 Source credentials are missing or invalid` — the source key is wrong, or you sent it to an
  operation that does not accept it.
- `403 The source is not allowed to accept traffic` — the source is disabled or not approved. Fix the
  source configuration; retrying will not help.
- `429` — 300 requests per 60 seconds against the organization-intake partition. Honour `Retry-After`
  (seconds). If the header is absent, back off exponentially with jitter. Leadping does not queue.

If a network timeout happens after submission, **check whether the lead was created before retrying** —
query by your `externalId` rather than posting again.
