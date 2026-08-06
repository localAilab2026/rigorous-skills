---
name: rigorous-feature
description: "Implement or modify a software feature in any language or repository. Use for ordinary backend, frontend, library, CLI, integration, or multi-file coding work when no more specialized rigorous skill is a better match. Ensures repository discovery, complete requirement coverage, minimal design, incremental implementation, independent verification, and evidence-based completion."
---

# Rigorous Feature Implementation

Implement the smallest complete change that satisfies the actual repository contract.

## Workflow

1. Inspect repository instructions, structure, build files, dependency versions, nearby patterns, public contracts, tests, and affected callers.
2. Run a baseline build or focused check when feasible; separate pre-existing failures.
3. Create an internal requirement ledger and acceptance oracle before coding.
4. Identify invariants, state changes, side effects, compatibility constraints, and highest-risk interactions.
5. Choose the smallest design that fits existing conventions. Avoid unrelated rewrites and speculative abstractions.
6. Implement in vertical increments; reread changed files and run focused checks after meaningful edits.
7. Add requirement-derived tests for normal, negative, boundary, repeated, and failure behavior.
8. Run integration or system checks where mocks would hide the changed boundary.
9. Switch to auditor mode: start from requirements, distrust the implementation and its tests, and attempt at least three plausible counterexamples.
10. Run the broadest relevant repository verification command.
11. Reconcile request, code, tests, configuration, migrations, and documentation.

## Non-negotiables

- Preserve existing behavior unless change is required.
- Do not hard-code sample outputs.
- Do not catch and ignore failures.
- Do not invent APIs, commands, files, or successful results.
- Do not mark a requirement optional merely because implementation is difficult.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
