---
name: rigorous-security
description: "Design, implement, audit, or harden security-sensitive software. Use for authentication, authorization, secrets, sessions, tokens, tenant isolation, untrusted input, uploads, cryptography usage, command execution, SSRF, injection, XSS, CSRF, CORS, deserialization, dependency risk, privacy, or security review."
---

# Rigorous Security Engineering

Start from assets, trust boundaries, attacker capabilities, and failure impact.

## Workflow

1. Identify protected assets, actors, trust boundaries, entry points, privileges, and sensitive data flows.
2. Define authentication separately from authorization; check object/resource-level and tenant-level authorization on every path.
3. Validate and constrain attacker-controlled input at the correct boundary; prefer allowlists and safe APIs.
4. Check injection, traversal, SSRF, unsafe deserialization, command execution, mass assignment, upload handling, and rendering contexts as applicable.
5. Protect secrets in storage, transit, logs, errors, tests, process arguments, and generated artifacts.
6. Define token/session creation, lifetime, rotation, revocation, replay protection, and clock behavior.
7. Fail closed on permission or policy uncertainty.
8. Bound expensive operations, body sizes, recursion, decompression, regex, queues, and retries against denial of service.
9. Use established cryptographic libraries and protocols; do not invent cryptography.
10. Test both allowed and denied behavior, privilege changes, cross-tenant access, malformed inputs, replay, and error leakage.
11. Review dependency and supply-chain exposure using repository-supported tools.
12. Report residual risk and threat assumptions explicitly.

## Evidence

Security claims require executable tests, framework configuration inspection, dependency evidence, or reproducible attack simulation—not only code comments.

## Optional reference

Load `references/threat-model.md` for security-sensitive changes or reviews.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
