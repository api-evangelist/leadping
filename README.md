# Leadping

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

Leadping is a lead-management and responsible-outreach platform for teams that need to move a new inbound lead from source to first touch without stitching together separate tools. It captures leads from approved sources, routes and assigns them, runs follow-up automations, sends SMS and MMS, places and transfers calls, keeps conversation and event history together, enforces recipient suppression and opt-out handling, tracks A2P 10DLC carrier registration and phone-number warmup, requires TrustedForm consent evidence where a source needs it, and reports usage, billing and analytics. The 137-operation REST API is published as an OpenAPI 3.1.1 contract with six Kiota-generated first-party SDKs, two remote MCP servers, Standard Webhooks signing, and an unusually complete machine-readable discovery surface including APIs.json, an RFC 9727 API catalog, RFC 9728 protected-resource metadata, llms.txt and an agent-skill index.

**Areas:** Lead Management · Sales & marketing automation · SMS Messaging · A2P 10DLC · CPaaS · Communications · Voice/calling · Compliance & consent · Agent-Native · MCP · Lead intake · Conversations

## Leadping on APIs.io

Everything profiled for Leadping is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/leadping/](https://apis.io/providers/leadping/)** — or go straight to one of the APIs or properties below.

### APIs (31)

- [Leadping MCP Servers](https://apis.io/apis/leadping/leadping-mcp-servers/) — Two remote Model Context Protocol servers. A public read-only documentation server at https://leadping.ai/docs/mcp answers anonymous tools/list with search,…
- [Leadping Webhook Events](https://apis.io/apis/leadping/leadping-webhook-events/) — Outbound HTTPS webhook deliveries fired by Leadping automations, signed with the Standard Webhooks specification (HMAC-SHA256 over…
- [Leadping Analytics API](https://apis.io/apis/leadping/leadping-analytics-api/) — Provides lead, communication, conversion, and organization performance analytics. Use these endpoints to measure activity over time, compare outcomes, and…
- [Leadping Automations API](https://apis.io/apis/leadping/leadping-automations-api/) — Manages automated lead follow-up workflows and their execution history. Use these endpoints to configure SMS automation steps, preview eligible leads, run…
- [Leadping Call Events API](https://apis.io/apis/leadping/leadping-callevents-api/) — Provides call event records for auditing, diagnostics, and reporting. Use these endpoints to search and inspect lifecycle events emitted as Leadping calls…
- [Leadping Calls API](https://apis.io/apis/leadping/leadping-calls-api/) — Manages outbound Leadping calls and active call-control workflows. Use these endpoints to initiate or cancel a call, retrieve call state, and transfer an…
- [Leadping Contact API](https://apis.io/apis/leadping/leadping-contact-api/) — Accepts public contact and website inquiry submissions for Leadping. Use these endpoints to send a structured support or sales inquiry from an application…
- [Leadping Conversations API](https://apis.io/apis/leadping/leadping-conversations-api/) — Provides lead conversation timelines and inbox-oriented conversation views. Use these endpoints to list recent conversations and retrieve the cross-channel…
- [Leadping Events API](https://apis.io/apis/leadping/leadping-events-api/) — Provides a unified record of Leadping activity across communication channels. Use these endpoints to retrieve event timelines, search event history, inspect…
- [Leadping Feedback API](https://apis.io/apis/leadping/leadping-feedback-api/) — Captures Leadping product feedback and supports administrative triage. Users can submit feedback, while authorized staff can search, inspect, classify, and…
- [Leadping Leads API](https://apis.io/apis/leadping/leadping-leads-api/) — Manages lead intake, records, assignment, routing, and lifecycle operations. Use these endpoints to ingest leads from trusted sources, search and update…
- [Leadping Lead Status Changes API](https://apis.io/apis/leadping/leadping-leadstatuschanges-api/) — Manages the auditable history of lead status transitions. Use these endpoints to change a lead's status, correct transition records, search status history,…
- [Leadping Notifications API](https://apis.io/apis/leadping/leadping-notifications-api/) — Manages user notifications, announcements, and push-notification installations. Use these endpoints to retrieve notification feeds and unread counts, update…
- [Leadping Organizations API](https://apis.io/apis/leadping/leadping-organizations-api/) — Manages Leadping organizations, memberships, invitations, settings, and API credentials. Use these endpoints to maintain organization profiles and branding,…
- [Leadping Outbound Delivery API](https://apis.io/apis/leadping/leadping-outbounddelivery-api/) — Reports outbound delivery pacing and sending capacity for the current organization. Use these endpoints to determine whether outbound communications can…
- [Leadping Sms API](https://apis.io/apis/leadping/leadping-sms-api/) — Sends and manages SMS and MMS communications through Leadping. Use these endpoints to send messages, upload MMS media, and cancel eligible scheduled…
- [Leadping Sms Events API](https://apis.io/apis/leadping/leadping-smsevents-api/) — Provides SMS and MMS event records for delivery tracking and diagnostics. Use these endpoints to search and inspect message lifecycle events, including…
- [Leadping Sources API](https://apis.io/apis/leadping/leadping-sources-api/) — Manages lead sources, intake credentials, routing defaults, and attribution. Use these endpoints to create and configure sources, search source records,…
- [Leadping Suppressions API](https://apis.io/apis/leadping/leadping-suppressions-api/) — Manages recipient suppression state for compliant Leadping communication workflows. Use these endpoints to check contact eligibility, record or release…
- [Leadping Tags API](https://apis.io/apis/leadping/leadping-tags-api/) — Manages organization-defined tags for categorizing and routing leads. Use these endpoints to list, create, update, and archive reusable tags that support…
- [Leadping Telephony API](https://apis.io/apis/leadping/leadping-telephony-api/) — Provides shared authentication and bootstrap data for Leadping telephony clients. Use this endpoint to obtain the scoped credentials and configuration…
- [Leadping Transactions API](https://apis.io/apis/leadping/leadping-transactions-api/) — Provides organization wallet and billing transaction records. Use these endpoints to search transaction history, inspect individual charges or credits,…
- [Leadping Usage API](https://apis.io/apis/leadping/leadping-usage-api/) — Provides billable usage records for Leadping services. Use these endpoints to review messaging and calling consumption, inspect usage summaries, and…
- [Leadping User Data Exports API](https://apis.io/apis/leadping/leadping-userdataexports-api/) — Creates and delivers user-requested exports of Leadping account data. Use these endpoints to request an export, monitor its preparation status, and download…
- [Leadping Users API](https://apis.io/apis/leadping/leadping-users-api/) — Manages the current Leadping user's profile, preferences, setup, and account workflows. Use these endpoints to retrieve and update user data, configure…
- [Leadping Wallets API](https://apis.io/apis/leadping/leadping-wallets-api/) — Manages organization wallet balances, funding, and credit activity. Use these endpoints to inspect wallet state and history, configure wallet behavior, add…
- [Leadping Blog Articles API](https://apis.io/apis/leadping/leadping-blogarticles-api/) — Provides published Leadping blog content. Use these endpoints to list published articles and retrieve an individual article by its public slug.
- [Leadping Leadping API](https://apis.io/apis/leadping/leadping-leadping-api-api/) — The Leadping API API from Leadping — 2 operation(s) for leadping api.
- [Leadping Lead Statuses API](https://apis.io/apis/leadping/leadping-lead-statuses-api/) — Manages the lead statuses used to classify and track leads throughout their lifecycle. Use these endpoints to list, create, update, and archive…
- [Leadping Payment Methods API](https://apis.io/apis/leadping/leadping-payment-methods-api/) — Manages organization payment methods and billing invoices. Use these endpoints to add, confirm, inspect, and remove payment methods or retrieve invoices…
- [Leadping Phone Numbers API](https://apis.io/apis/leadping/leadping-phone-numbers-api/) — Manages phone-number discovery, purchasing, assignment, configuration, and compliance. Use these endpoints to search available numbers, manage owned numbers…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Leadping Webhooks](https://apis.io/asyncapis/leadping/leadping-webhooks/)

#### MCP servers (2)

Model Context Protocol servers that expose the API to agents.

- [leadping-mcp.yml](https://apis.io/servers/leadping/leadping-mcp-yml/)
- [mcp](https://apis.io/servers/leadping/mcp/)

#### Overlays (30)

OpenAPI overlays, including conversational phrasing for each operation.

- [Leadping Analytics Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-analytics-api-phrasing-overlay/)
- [Leadping Api Overlay](https://apis.io/overlays/leadping/leadping-api-overlay/)
- [Leadping Automations Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-automations-api-phrasing-overlay/)
- [Leadping Blogarticles Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-blogarticles-api-phrasing-overlay/)
- [Leadping Callevents Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-callevents-api-phrasing-overlay/)
- [Leadping Calls Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-calls-api-phrasing-overlay/)
- [Leadping Contact Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-contact-api-phrasing-overlay/)
- [Leadping Conversations Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-conversations-api-phrasing-overlay/)
- [Leadping Events Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-events-api-phrasing-overlay/)
- [Leadping Feedback Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-feedback-api-phrasing-overlay/)
- [Leadping Lead Statuses Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-lead-statuses-api-phrasing-overlay/)
- [Leadping Leadping Api Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-leadping-api-api-phrasing-overlay/)
- [Leadping Leads Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-leads-api-phrasing-overlay/)
- [Leadping Leadstatuschanges Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-leadstatuschanges-api-phrasing-overlay/)
- [Leadping Notifications Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-notifications-api-phrasing-overlay/)
- [Leadping Organizations Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-organizations-api-phrasing-overlay/)
- [Leadping Outbounddelivery Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-outbounddelivery-api-phrasing-overlay/)
- [Leadping Payment Methods Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-payment-methods-api-phrasing-overlay/)
- [Leadping Phone Numbers Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-phone-numbers-api-phrasing-overlay/)
- [Leadping Sms Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-sms-api-phrasing-overlay/)
- [Leadping Smsevents Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-smsevents-api-phrasing-overlay/)
- [Leadping Sources Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-sources-api-phrasing-overlay/)
- [Leadping Suppressions Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-suppressions-api-phrasing-overlay/)
- [Leadping Tags Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-tags-api-phrasing-overlay/)
- [Leadping Telephony Api Phrasing Overlay](https://apis.io/overlays/leadping/leadping-telephony-api-phrasing-overlay/)
- …and 5 more published on APIs.io

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Leadping Authentication](https://apis.io/security/leadping/leadping-authentication/)
- [Leadping Domain Security](https://apis.io/security/leadping/leadping-domain-security/)
- [Leadping Trust Center](https://apis.io/security/leadping/leadping-trust-center/)
- [Leadping Vulnerability Disclosure](https://apis.io/security/leadping/leadping-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Leadping Scopes](https://apis.io/scopes/leadping/leadping-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Leadping Plans Pricing](https://apis.io/plans/leadping/leadping-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Leadping Rate Limits](https://apis.io/rate-limits/leadping/leadping-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://leadping.ai/)
- [Documentation](https://leadping.ai/docs)
- [Getting started](https://leadping.ai/docs/get-started)
- [API reference](https://leadping.ai/docs/api-reference)
- [Pricing](https://leadping.ai/pricing)
- [Sign up](https://leadping.ai/authentication/login)
- [Support](https://leadping.ai/contact)
- [Changelog](https://api.leadping.ai/changelog.json)
- [Blog](https://leadping.ai/blog)
- [Compliance](https://leadping.ai/docs/compliance)
- [Terms of service](https://leadping.ai/docs/terms-of-service)
- [Privacy policy](https://leadping.ai/docs/privacy-policy)
- [GitHub](https://github.com/leadpingai)
- [Status](https://status.leadping.ai)

## API Evangelist rating

**Kin Score 75.4** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 85.0 |
| Contract quality | 63.8 |
| Contract governance | 31.8 |
| Operational transparency | 76.3 |
| Developer ergonomics | 73.2 |
| Access clarity | 81.6 |

**Agent readiness 71.7** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | yes |
| Reversibility Documented | documented (partial credit) |
| MCP Server | documented (partial credit) |
| Auth Clarity | served (partial credit) |
| Idempotency | verified |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | verified |
| Event Surface Described | yes |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | yes |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | yes |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | — |
| Operation Distinctiveness | distinct |

**Regulatory alignment 48.3** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/leadping/](https://apis.io/providers/leadping/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Leadping: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/leadping/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
