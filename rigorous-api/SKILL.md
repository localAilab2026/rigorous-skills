---
name: rigorous-api
description: "Design, implement, debug, or review HTTP/REST APIs, controllers, clients, webhooks, authentication integrations, request/response schemas, pagination, error contracts, retries, or external service calls. Use for backend endpoints and API-consuming code where protocol correctness, compatibility, validation, and failure behavior matter."
---

# Rigorous API Engineering

Treat the wire contract and externally visible behavior as primary.

## Workflow

1. Inspect existing routes, schemas, auth, clients, error format, versioning, and generated contracts.
2. Specify method, path, headers, content types, body schema, status codes, error codes, ordering, pagination, and compatibility.
3. Separate syntax validation, authentication, authorization, business validation, and conflict handling.
4. Define idempotency, duplicate requests, retries, timeouts, cancellation, and partial external failure.
5. Keep transaction boundaries explicit; avoid slow external calls inside database transactions unless justified.
6. Preserve stable response fields and semantics for existing clients.
7. Implement consistent error handling without leaking secrets or internals.
8. Test malformed bodies, missing headers, unsupported media types, auth failures, resource-level authorization, conflicts, limits, duplicate calls, and downstream failures.
9. Use real serialization/framework integration tests for critical contracts.
10. Verify observability without logging credentials, tokens, or sensitive payloads.

## Client-specific checks

- connection and read timeout,
- retry safety by operation type,
- backoff and retry exhaustion,
- response size and streaming,
- schema drift and unknown fields,
- cancellation and resource closure.

## Optional reference

Load `references/api-contract.md` when defining or validating a public wire contract.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
