# PolicyCheck

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

PolicyCheck (formerly LegalEasy) is a seller-policy risk intelligence service built for AI purchasing agents. Given a store URL or raw policy text it extracts structured facts from return, shipping, warranty, terms and privacy policies — return window, restocking fees, binding arbitration, class-action waivers, data selling — scores them deterministically into a 0-10 risk score and a 0-100 buyer protection score, labels standard boilerplate separately from unusual restrictions, and can return the result as an Ed25519-signed assessment an agent presents at checkout and a merchant verifies against a public JWKS. The surface is anonymous REST at policycheck.tools/api/check, an A2A JSON-RPC agent with a published agent card, a stdio MCP server on npm, an x402 pay-per-analysis endpoint settled in USDC on Base, a versioned clause registry, and a keyed audit log and compliance report. The published OpenAPI covers only the two legacy ChatGPT-plugin operations.

**Areas:** Company · Policy Analysis · Consumer Protection · E-Commerce · Agentic Commerce · Risk Assessment · AI Agents · A2A · MCP · x402 · Legal · Returns

## PolicyCheck on APIs.io

Everything profiled for PolicyCheck is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/policycheck-tools/](https://apis.io/providers/policycheck-tools/)** — or go straight to one of the APIs or properties below.

### APIs (4)

- [PolicyCheck A2A Agent](https://apis.io/apis/policycheck-tools/policycheck-a2a-agent/) — JSON-RPC 2.0 Agent-to-Agent endpoint at https://policycheck.tools/api/a2a, discovered through an A2A agent card served at the legacy /.well-known/agent.json…
- [PolicyCheck MCP Server](https://apis.io/apis/policycheck-tools/policycheck-mcp-server/) — The policycheck-mcp npm package (1.0.2, published 2026-02-13, MIT) is a stdio Model Context Protocol server installed with `npx -y policycheck-mcp`. It…
- [PolicyCheck x402 Analysis API](https://apis.io/apis/policycheck-tools/policycheck-x402-analysis-api/) — Pay-per-request analysis over the x402 protocol: POST https://policycheck.tools/api/x402/analyze answers HTTP 402 with a PAYMENT-REQUIRED header carrying an…
- [PolicyCheck Chatgpt API](https://apis.io/apis/policycheck-tools/policycheck-tools-chatgpt-api/) — The Chatgpt API from PolicyCheck — 2 operation(s) for chatgpt.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [policycheck-mcp](https://apis.io/servers/policycheck-tools/policycheck-mcp/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Policycheck Tools Agentic Access](https://apis.io/agentic-access/policycheck-tools/policycheck-tools-agentic-access/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Policycheck Tools Openapi Overlay](https://apis.io/overlays/policycheck-tools/policycheck-tools-openapi-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Policycheck Tools Authentication](https://apis.io/security/policycheck-tools/policycheck-tools-authentication/)
- [Policycheck Tools Domain Security](https://apis.io/security/policycheck-tools/policycheck-tools-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Policycheck Tools Plans Pricing](https://apis.io/plans/policycheck-tools/policycheck-tools-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Policycheck Tools Rate Limits](https://apis.io/rate-limits/policycheck-tools/policycheck-tools-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://policycheck.tools/)
- [Documentation](https://policycheck.tools/docs)
- [Getting started](https://policycheck.tools/docs#quick-start)
- [API reference](https://policycheck.tools/docs#endpoints)
- [Pricing](https://policycheck.tools/docs#rate-limits)
- [Blog](https://policycheck.tools/blog)
- [Terms of service](https://policycheck.tools/legal)
- [Privacy policy](https://policycheck.tools/legal)
- [GitHub](https://github.com/vibegpt)

## API Evangelist rating

**Kin Score 45.4** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 63.3 |
| Contract quality | 44.7 |
| Contract governance | 18.2 |
| Operational transparency | 26.3 |
| Developer ergonomics | 49.4 |
| Access clarity | 52.6 |

**Agent readiness 37.0** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 32.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/policycheck-tools/](https://apis.io/providers/policycheck-tools/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for PolicyCheck: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/policycheck-tools/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
