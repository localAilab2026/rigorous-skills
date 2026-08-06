---
name: rigorous-code-review
description: "Review, compare, score, or audit source code, pull requests, generated projects, model submissions, patches, or repositories. Use when evaluating correctness, architecture, maintainability, tests, security, performance, concurrency, or requirement compliance. Treats documentation and existing tests as claims, runs independent checks, and reports severity with evidence."
---

# Rigorous Code Review

Review from the specification outward, not from the author's explanation inward.

## Workflow

1. Establish the requested contract and repository baseline.
2. Inspect the complete diff and affected consumers, not only highlighted files.
3. Build a requirement-to-evidence ledger.
4. Compile and run submitted tests when possible, but do not treat passing tests as sufficient.
5. Inspect control flow, data mutation, error paths, resource lifetime, trust boundaries, compatibility, and state transitions.
6. Compare README/comments/claims against executable behavior.
7. Construct independent adversarial cases and run targeted harnesses where feasible.
8. Look for interactions missed by existing tests and for test setup that masks defects.
9. Rank findings by severity, reproducibility, likelihood, and blast radius.
10. Distinguish confirmed defects, likely risks, style concerns, and unverified claims.
11. Score only against an explicit rubric; explain deductions with evidence.
12. State what could not be verified and why.

## Finding format

For every material finding provide:

- severity,
- violated requirement or invariant,
- evidence and location,
- reproducible scenario,
- impact,
- minimal corrective direction,
- missing test.

Do not inflate minor style preferences into correctness failures.

## Optional reference

Load `references/review-checklist.md` for broad repository, pull-request, or benchmark audits.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
