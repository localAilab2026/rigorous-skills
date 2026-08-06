---
name: rigorous-distributed
description: "Design, implement, debug, or review distributed systems, microservices, message consumers, queues, event-driven workflows, transactional outbox, sagas, retries, idempotency, caching, distributed locks, service-to-service calls, or eventual consistency. Use when failures can occur between independent processes or durable systems."
---

# Rigorous Distributed Systems

Assume networks fail ambiguously and delivery may be duplicated, delayed, reordered, or lost according to the actual transport contract.

## Workflow

1. Draw the durable state machines and ownership boundaries for every participating service or store.
2. State delivery and consistency guarantees honestly.
3. Define stable operation/event identity and idempotency behavior for same payload, conflicting payload, concurrent retry, replay after restart, and retention expiry.
4. Model crash points between state mutation, publication, acknowledgement, and response.
5. Define timeout semantics: distinguish unknown outcome from confirmed failure.
6. Define retries, exponential backoff, jitter, retryable classes, attempt limits, poison handling, and dead-letter behavior.
7. Handle duplicates, ordering, partitioning, mixed versions, and schema evolution.
8. Avoid holding database transactions across slow network calls unless the design explicitly proves the trade-off.
9. For outbox/inbox patterns, test restart, duplicate publisher/consumer instances, claim expiry, and failure after broker acceptance.
10. Test partial availability, retry storms, stale caches, clock differences, and recovery.
11. Add observability using correlation and stable event IDs without leaking sensitive data.
12. Document what clients should do after ambiguous timeout or conflict.

## Guarantee language

Use terms such as at-most-once, at-least-once, effectively-once for a scoped effect, eventual consistency, or best effort only when demonstrated. Do not claim global exactly-once delivery without an atomic protocol spanning every relevant system.

## Optional reference

Load `references/crash-point-table.md` when work crosses durable systems or acknowledgements.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
