---
name: rigorous-specification
description: "Analyze and clarify programming requirements before implementation. Use for implementation plans, architecture proposals, ambiguous feature requests, acceptance criteria, task decomposition, repository-impact analysis, or when a coding task must be converted into a precise, independently verifiable contract without silently adding or weakening requirements."
---

# Rigorous Specification

Create a specification that an implementer and an independent reviewer can both use.

## Workflow

1. Read the request and applicable repository instructions.
2. Inspect existing contracts, callers, schemas, tests, configuration, and deployment assumptions before proposing change.
3. Separate facts, explicit requirements, assumptions, ambiguities, optional improvements, and out-of-scope ideas.
4. Build a requirement ledger with one row per observable requirement:
   - source,
   - input/precondition,
   - expected output or state transition,
   - forbidden outcome,
   - compatibility impact,
   - verification evidence.
5. Define an independent acceptance oracle before proposing implementation details.
6. Specify exact boundaries: inclusive/exclusive thresholds, ordering, time, precision, errors, retries, cancellation, and partial failure.
7. Model important interactions between requirements, not only each rule independently.
8. Identify affected modules and consumers using repository evidence.
9. Propose the smallest complete design and alternatives only where trade-offs materially differ.
10. Produce a verification plan that can falsify the future implementation.

## Required output

- Ground truth and repository context
- Requirement ledger
- Acceptance oracle
- Assumptions and unresolved ambiguities
- Affected surface
- Design and trade-offs
- Verification matrix
- Risks and rollback/compatibility notes

Do not encode a preferred implementation as if it were a requirement.

## Optional reference

Load `references/oracle-template.md` when producing a formal acceptance contract or handoff specification.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
