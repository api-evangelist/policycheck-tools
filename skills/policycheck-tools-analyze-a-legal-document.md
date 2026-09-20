---
generated: '2026-09-19'
method: generated
name: Analyze a seller's legal document for buyer risk
description: Run PolicyCheck's contracted analysis over a policy document — by raw text or by URL — and read the risk flags correctly before acting on a purchase.
api: openapi/policycheck-tools-openapi.yml
operations: [analyzeLegalDocument, analyzeLegalDocumentFromURL]
source: >-
  Grounded in openapi/policycheck-tools-openapi.yml, captured verbatim 2026-09-19 from
  https://policycheck.tools/openapi.json. Both operationIds verified in that spec. Auth per
  authentication/policycheck-tools-authentication.yml, errors per errors/policycheck-tools-problem-types.yml,
  semantics per conventions/policycheck-tools-conventions.yml. The richer documented endpoint POST /api/check
  is named where relevant but is NOT in the published contract.
---

# Analyze a seller's legal document for buyer risk

PolicyCheck turns a return policy, terms of service, privacy policy or shipping policy into structured risk
data. The two operations in its published OpenAPI are the legacy ChatGPT-plugin pair; both are live and
anonymous.

## Auth
- None. Neither operation requires a credential (`authentication/policycheck-tools-authentication.yml`).
- Base URL: `https://policycheck.tools`.

## Steps

1. **Decide text or URL.** If you already hold the policy text (you rendered the page, or the user pasted it),
   use `analyzeLegalDocument` (`POST /api/chatgpt/analyze`) with `{"text": "...", "document_type": "terms|privacy|refund|shipping|other", "product_name": "optional"}`.
   `text` is required; `document_type` defaults to `terms`.
2. **Otherwise analyze by URL** with `analyzeLegalDocumentFromURL` (`POST /api/chatgpt/analyze-url`) and
   `{"url": "https://store.example/policies/refund-policy", "document_type": "refund"}`. The server fetches
   and extracts the page itself.
3. **Read the response.** `summary.sections[]` (key, title, bullets, body) is the plain-English digest;
   `risks` carries booleans `arbitration`, `classActionWaiver`, `terminationAtWill` plus nullable numbers
   `liabilityCap` and `optOutDays`; `key_findings[]` is the short list to surface to a human.
4. **Escalate, do not decide.** PolicyCheck is an intelligence provider, not a gatekeeper: it returns facts and
   risk classifications, never a "safe to buy" verdict. Apply the user's own dealbreakers (for example
   `risks.arbitration === true`) and ask the human when a dealbreaker matches.

## Rules an agent must follow

- **JS-rendered and bot-protected stores fail server-side fetch.** If the URL path returns thin or empty
  content, render the page yourself and resend the text via `analyzeLegalDocument`. The docs name Temu and
  Best Buy as sites that cannot be fetched server-side.
- **Retries are safe.** Both operations are read/compute with no write surface, so a timeout or `500` can be
  retried with backoff; there is no idempotency key because none is needed
  (`conventions/policycheck-tools-conventions.yml`).
- **Errors are `{"error": string}`.** `400` means a missing/invalid `text` or `url`; `500` is a server error.
  No error codes, no RFC 9457 (`errors/policycheck-tools-problem-types.yml`).
- **Rate limit.** The agent card states 100 requests/minute for the free tier; no limit headers are returned,
  so pace yourself rather than waiting for a 429 (`rate-limits/policycheck-tools-rate-limits.yml`).
- **Not legal advice.** The provider's terms say the analysis is AI-generated and may contain errors; every
  finding should be presented as a flag to check, not as a legal conclusion.
- **Need the richer schema or a signed result?** The documented but uncontracted `POST /api/check` returns
  `risk_score`, `buyer_protection_score`, `flags[]` (stable clause-registry ids), `analysis_status` and
  `confidence`; `POST /api/v1/signed-assessment` returns the same inside an Ed25519-signed envelope that
  expires in 5 minutes. Treat `analysis_status: "no_content"` as *no data*, never as a clean seller.
