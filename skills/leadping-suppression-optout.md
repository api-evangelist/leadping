---
name: leadping-suppression-optout
description: Honour an opt-out, check suppression before contact, and audit an organization's Leadping suppression list.
api: Leadping API
base_url: https://api.leadping.ai
generated: '2026-08-18'
method: generated
source: openapi/leadping-openapi.json + https://leadping.ai/docs/acceptable-use
operations:
  - Suppressions_Check
  - Suppressions_Suppress
  - Suppressions_Release
  - Suppressions_Get
  - Suppressions_GetAllForCurrentOrganization
---

# Honour opt-outs with Leadping suppression

Suppression is Leadping's contact-blocking control. Treat it as the gate in front of every outbound
message or call, not as an after-the-fact cleanup.

## Credential

`Authorization: Bearer sk_...` (organization API key) or a Leadping user access token.

## Check before contact

`Suppressions_Check` (`POST /suppressions/check`) returns a `SuppressionCheckResult` naming the
`organizationId` and, on a hit, the `suppressionEntryId`. A hit means **do not contact**. Run this
before `Sms_Send` and before `Calls_InitiateCall`.

## Record an opt-out

`Suppressions_Suppress` (`POST /suppressions`) creates or reactivates a recipient suppression. Call it
the moment a recipient asks to stop — by reply keyword, on a call, by email, or through any other
channel your team operates. Suppression state is per organization.

## Release a suppression

`Suppressions_Release` (`POST /suppressions/release`) releases an active suppression. This is a
consequential operation: releasing a suppression makes a previously opted-out person contactable again.
Only do it with a documented, affirmative new consent. If you are not certain, do not release.

## Audit

- `Suppressions_Get` (`GET /suppressions/{id}`) reads one entry.
- `Suppressions_GetAllForCurrentOrganization` (`POST /suppressions/all/my`) lists the organization's
  entries. It is a POST list operation taking a `RequestDataOptions` body — set `pageSize`, page with the
  opaque `continuationToken`, and set `includeCount` only when you actually need a total (counting costs
  latency).

`SuppressionEntryAudit` records who changed an entry (`actorId`), which is what you show when a dispute
or carrier review asks how an opt-out was handled.

## Error handling

Errors are RFC 9457 Problem Details. `403` means the credential lacks permission for the organization;
`429` means 300 req/60s exhausted — honour `Retry-After`.
