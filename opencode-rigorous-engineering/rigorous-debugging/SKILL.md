---
name: rigorous-debugging
description: "Diagnose and fix software defects, failing tests, exceptions, regressions, incorrect output, intermittent behavior, startup failures, or integration problems. Use when the user provides errors, logs, stack traces, failing code, or asks why behavior is wrong. Prioritizes reproducible evidence, root-cause isolation, minimal fixes, and regression protection."
---

# Rigorous Debugging

Treat the observed symptom as evidence, not automatically as the root cause.

## Workflow

1. Capture the exact symptom, environment, inputs, expected behavior, actual behavior, and reproducibility.
2. Inspect recent changes, logs, stack traces, configuration, dependency versions, and nearby code paths.
3. Reproduce with the smallest reliable case. If reproduction is impossible, state what evidence is missing.
4. Establish a working baseline or compare with a known-good path.
5. Generate competing hypotheses ranked by evidence and discriminating tests.
6. Instrument or run focused experiments to eliminate hypotheses; avoid speculative edits.
7. Trace data and control flow across boundaries until the first violated invariant is found.
8. Fix the root cause with the smallest safe change.
9. Add a regression test that fails before the fix and passes after it.
10. Check adjacent cases, alternate paths, cleanup, retries, and compatibility.
11. Remove temporary diagnostics unless intentionally retained.
12. Run focused and broad verification.

## Guardrails

- Do not suppress errors to make tests pass.
- Do not increase timeouts or retries without evidence that timing is the cause.
- Do not rewrite large areas before isolating the defect.
- For intermittent bugs, test concurrency, ordering, clocks, resource exhaustion, and shared state.

## Optional reference

Load `references/hypothesis-log.md` when the defect has multiple plausible causes or requires several experiments.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
