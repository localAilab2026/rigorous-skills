---
name: rigorous-testing
description: "Design, implement, improve, or audit automated tests for any programming project. Use for unit, integration, end-to-end, property, mutation, concurrency, compatibility, or benchmark tests; weak coverage; flaky tests; test strategy; or when existing tests may validate implementation details instead of requirements."
---

# Rigorous Testing

Tests must be capable of proving an implementation wrong.

## Workflow

1. Derive expected behavior from requirements and existing contracts before reading or copying implementation logic.
2. Build a verification matrix mapping every material requirement to evidence.
3. Choose the lowest test layer that observes the real risk; use integration boundaries when mocks would hide defects.
4. Cover normal, negative, empty, malformed, duplicate, unsupported, minimum, exact-boundary, maximum, overflow, repeated, and partial-failure behavior as relevant.
5. Test interactions between requirements, such as retry plus concurrency or rounding plus aggregation.
6. For each test, name the plausible bug it should catch.
7. Use deterministic control for time, concurrency, randomness, filesystem, network, and external services.
8. Verify both intended effects and absence of forbidden side effects.
9. Check stable ordering, reproducibility, cleanup, isolation, and execution-order independence.
10. Use mutation thinking: determine whether a plausible broken implementation would still pass.
11. Run focused tests repeatedly where flakiness is a risk, then run the broad suite.

## Reject weak tests

Reject or strengthen tests that:

- copy expected values from production code,
- assert internal calls instead of behavior,
- accidentally serialize concurrency,
- rely on arbitrary sleeps,
- accept several outcomes without proving each legal,
- pass when core logic is replaced by a trivial stub,
- test only the happy path,
- encode the current implementation's interpretation of an ambiguous requirement.

## Optional reference

Load `references/verification-matrix.md` when coverage spans multiple requirements or test layers.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
