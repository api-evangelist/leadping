---
name: leadping-first-response-sms
description: Send a compliant first-touch SMS or MMS to a new Leadping lead, checking suppression and sender readiness first, with duplicate-send protection.
api: Leadping API
base_url: https://api.leadping.ai
generated: '2026-08-18'
method: generated
source: openapi/leadping-openapi.json + https://leadping.ai/docs/compliance
operations:
  - Suppressions_Check
  - PhoneNumbers_GetOutgoingForNewOutbound
  - PhoneNumbers_GetStatus
  - Sms_UploadMedia
  - Sms_Send
  - Sms_CancelScheduled
  - Conversations_GetConversationsByLead
  - Events_GetAllForLead
---

# Send a first-response SMS to a Leadping lead

Use this when a lead has arrived and the organization wants to text them. This is a **consequential**
flow: it sends real messages to real people through a carrier, and Leadping's acceptable-use rules
apply.

## Credential

`Authorization: Bearer sk_...` (organization API key) or a Leadping user access token. A `lp_src_`
source key will be rejected.

## Before you send

1. **Check suppression.** Call `Suppressions_Check` (`POST /suppressions/check`) for the recipient. If
   the recipient is suppressed, stop. Do not send. Suppression carries opt-out and DNC handling.
2. **Confirm the message matches the consent.** Leadping's compliance guidance is a three-question test:
   where did the lead come from, what did the person agree to receive and from whom, and does this
   outreach match that agreement. If any answer is unclear, pause.
3. **Pick a ready sender.** Call `PhoneNumbers_GetOutgoingForNewOutbound`
   (`POST /phone-numbers/outgoing/new`) to let Leadping select the sender number. Check readiness with
   `PhoneNumbers_GetStatus` (`GET /phone-numbers/{phoneNumber}/status`) or
   `PhoneNumbers_GetWarmupStatus` if the number is new — production SMS depends on carrier
   registration state.

## Send

4. **Attach media first, if any.** `Sms_UploadMedia` (`POST /sms/media`). Supplying at least one entry in
   `mediaUrls` makes the send an MMS, which is billed at a different rate.
5. **Send.** `Sms_Send` (`POST /sms/send`) with a `SendSmsRequest`: `conversationId`, `text`, optional
   `mediaUrls`, optional `campaignId` / `sourceId` / `fromPhoneNumberId`.
6. **Set `outboundIdempotencyKey`.** This is the only idempotency mechanism Leadping offers, it lives in
   the request body (there is no `Idempotency-Key` header), and it is scoped to preventing duplicate
   outbound delivery. Use a key derived from the lead and the intent, not a random value, so a retry
   after a timeout reuses it. The retention window is not published — treat it as short.
7. **Cancel if needed.** `Sms_CancelScheduled` (`POST /sms/{smsEventId}/cancel`) cancels a scheduled
   message that has not yet gone out.

## Confirm

8. Read the outcome with `Events_GetAllForLead` (`POST /events/leads/{leadId}`) or
   `Conversations_GetConversationsByLead` (`POST /conversations/lead/{leadId}`). Both are POST list
   operations that take a `RequestDataOptions` body — pass `continuationToken` to page, do not parse it.

## Error handling

- `403 The authenticated user or organization does not have permission` — check organization membership,
  role, and that you are not using a source key.
- `429` — 300 requests per 60 seconds. Honour `Retry-After`; back off with jitter if absent.
- On any timeout, **retry with the same `outboundIdempotencyKey`** rather than composing a new send.
