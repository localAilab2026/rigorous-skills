---
name: rigorous-concurrency
description: "Implement, debug, or review multithreaded, asynchronous, parallel, reactive, actor-based, or shared-state code. Use for locks, atomics, executors, futures, caches, reservations, schedulers, lifecycle races, deadlocks, visibility, linearizability, cancellation, backpressure, or concurrency tests."
---

# Rigorous Concurrency

A concurrency guarantee requires a model of legal executions and adversarial evidence.

## Workflow

1. List every shared mutable object, its owner, and every operation that reads or writes it.
2. Define invariants, legal state transitions, linearization points, and valid serial outcomes.
3. Specify memory visibility and safe publication, not only mutual exclusion.
4. Define one global resource-acquisition order and apply it to every code path, including cleanup and error handling.
5. Analyze same, overlapping, and disjoint resource sets.
6. Analyze conflicts among normal operations, retries, cancellation, timeout, cleanup, shutdown, and expiration.
7. Bound waits, queues, retries, tasks, buffers, and resource use.
8. Implement the smallest synchronization scheme that proves the invariants.
9. Build deterministic tests using barriers, latches, futures, controlled schedulers, virtual time, and repeated stress; do not use sleeps as the correctness mechanism.
10. Test double execution, conflicting transitions, stale observation, snapshot consistency, same-key retries, lock-order cycles, executor saturation, and interruption.
11. Use deadlock detection or time-bounded harnesses where relevant.
12. State the actual guarantee precisely: thread-safe, race-free for named operations, linearizable, eventually consistent, or weaker.

## Auditor questions

- Can a snapshot observe a state that is impossible in any serial execution?
- Does cleanup enforce business semantics, or merely optimize them?
- Can two maps or fields publish one logical record partially?
- Does test setup accidentally serialize the race?

## Optional reference

Load `references/concurrency-matrix.md` when two or more operations can overlap.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
