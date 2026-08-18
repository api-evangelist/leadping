---
name: leadping-lead-lifecycle
description: Work an existing Leadping lead — page the list, read it, move its status, tag it, and archive or delete it.
api: Leadping API
base_url: https://api.leadping.ai
generated: '2026-08-18'
method: generated
source: openapi/leadping-openapi.json
operations:
  - Leads_GetAllForCurrentUser
  - Leads_GetForCurrentUser
  - Leads_Update
  - Leads_Archive
  - Leads_Unarchive
  - Leads_Delete
  - Leads_AddTags
  - Leads_ReplaceTags
  - Leads_RemoveTag
  - LeadStatuses_GetAll
  - LeadStatusChanges_SetCurrent
  - LeadStatusChanges_GetByLeadId
  - Leads_GetWorkflowStatusForCurrentUser
---

# Work a Leadping lead

## Credential

`Authorization: Bearer sk_...` (organization API key) or a Leadping user access token.

## Paging the list — read this first

`Leads_GetAllForCurrentUser` is `POST /leads/all/my`, **not** a GET with query parameters. Every Leadping
list endpoint works this way: the filter, sort, search and paging instructions travel in a
`RequestDataOptions` JSON body.

```json
{
  "pageSize": 50,
  "continuationToken": null,
  "includeCount": false,
  "orderBy": [{ "field": "createdAt", "direction": "desc" }],
  "search": "acme",
  "searchFields": ["companyName"]
}
```

The response is a `PagedResultOfLeadTableRow`. Pass the returned `continuationToken` back on the next
call. It is opaque — do not parse or modify it. Leave `includeCount` false unless you need the total;
counting increases query cost and latency.

## Read one lead

`Leads_GetForCurrentUser` (`GET /leads/{id}`). `Leads_GetWorkflowStatusForCurrentUser`
(`GET /leads/{id}/workflow-status`) reports where the lead sits in its automation workflow.

## Move the status

1. `LeadStatuses_GetAll` (`GET /lead-statuses`) lists the organization's defined statuses.
2. `LeadStatusChanges_SetCurrent` (`PUT /leads/{leadId}/status`) sets the current status.
3. `LeadStatusChanges_GetByLeadId` (`GET /leads/{leadId}/status-history`) reads the audit trail;
   `LeadStatusChanges_ExportByLeadId` exports it.

Every status change records `changedByUserId` or `changedByAutomationId`, and may link the
`relatedCallEventId` that caused it.

## Tag

`Leads_AddTags` (`POST /leads/{id}/tags`) adds, `Leads_ReplaceTags` (`PUT`) replaces the whole set, and
`Leads_RemoveTag` (`DELETE /leads/{id}/tags/{tagId}`) removes one. Tags themselves are organization
resources managed through `Tags_Create` / `Tags_Update` / `Tags_Archive`.

## Retire

- `Leads_Archive` (`POST /leads/{id}/archive`) and `Leads_Unarchive` are reversible. Prefer these.
- `Leads_Delete` (`DELETE /leads/{id}`) is **permanent**. Leadping's MCP tooling flags it as
  consequential and requires explicit confirmation; hold your own agent to the same bar.

## Error handling

RFC 9457 Problem Details throughout. `401 The user does not own this lead` and
`404 The specified lead was not found` are distinct — the first is an authorization failure against a
lead that exists. `429` is 300 req/60s; honour `Retry-After`.
