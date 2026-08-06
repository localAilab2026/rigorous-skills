---
name: rigorous-data
description: "Design, implement, migrate, debug, or review databases, ORM code, transactions, repositories, schemas, migrations, file imports, ETL, batch processing, reconciliation, or exact numeric calculations. Use when durable data, consistency, rollback, schema evolution, ordering, precision, or restart behavior is central."
---

# Rigorous Data and Persistence

Protect durable truth and make partial failure explicit.

## Workflow

1. Inspect schema, constraints, indexes, ORM mappings, transaction settings, migration history, data volume, and existing data contracts.
2. Define invariants at both application and database levels.
3. Specify transaction boundaries, isolation assumptions, locking/versioning, retries, and retry exhaustion.
4. Model failure after each durable mutation and define rollback or recovery.
5. For migrations, define forward compatibility, backfill, mixed-version operation, rollback, restart, and observability.
6. For imports/ETL, define encoding, delimiter/schema, malformed-row policy, duplicate policy, stable ordering, checkpointing, replay, and rejected-record reporting.
7. Use exact numeric types and explicitly define units, currency, scale, rounding mode, and rounding stage.
8. Prevent N+1 queries, unbounded loads, hidden full scans, and inconsistent pagination.
9. Test constraints, transaction rollback, concurrent updates, restart, old data, large data, malformed data, and reconciliation totals.
10. Verify persisted snapshots remain stable after source configuration or prices change.

## Prohibitions

- Do not rely solely on application validation for critical integrity.
- Do not mix incompatible currencies or units.
- Do not claim exactly-once processing without a proven end-to-end mechanism.

## Optional reference

Load `references/failure-injection.md` for transactional, migration, restart, or durable-work flows.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
