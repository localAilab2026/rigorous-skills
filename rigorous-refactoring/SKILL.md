---
name: rigorous-refactoring
description: "Refactor, reorganize, rename, split, simplify, modernize, or migrate code while preserving required behavior. Use for large-file decomposition, architecture cleanup, language or framework migration, dependency replacement, legacy modernization, or requests explicitly requiring no functional behavior changes."
---

# Rigorous Refactoring

Preserve behavior unless the request explicitly changes it.

## Workflow

1. Identify observable behavior, public contracts, serialization, configuration, data, performance, and operational assumptions that must remain stable.
2. Run baseline tests and add characterization tests for poorly covered behavior before structural change.
3. Map callers, reflection, dependency injection, generated code, templates, resources, scripts, and deployment references.
4. Define migration stages and mixed old/new compatibility where the refactor cannot be atomic.
5. Make small mechanical changes first; separate behavior changes into explicit commits or patches.
6. Compile and test after each structural slice.
7. Preserve error types, defaults, ordering, precision, side effects, threading, and lifecycle unless intentionally changed.
8. Remove old code only after all consumers and data have migrated.
9. Compare before/after behavior with representative and edge inputs.
10. Check performance and operability regressions, not only functional tests.
11. Update documentation and configuration only where the new structure requires it.

## Migration guardrails

- Do not combine broad cleanup with unrelated feature changes.
- Do not rely only on compilation to prove equivalence.
- For data/schema migration, define forward path, backfill, rollback, restart behavior, and mixed-version operation.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
