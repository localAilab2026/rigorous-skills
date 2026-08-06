---
name: rigorous-performance
description: "Analyze, benchmark, or optimize latency, throughput, memory, CPU, allocation, I/O, database access, startup, scalability, or resource use. Use for slow code, performance regressions, capacity planning, large datasets, load behavior, or optimization proposals. Requires measurement before and after and preserves correctness."
---

# Rigorous Performance Engineering

Optimize measured bottlenecks while preserving the acceptance oracle.

## Workflow

1. Define the target metric, workload, percentile, concurrency, data distribution, environment, and acceptable resource bounds.
2. Establish correctness tests and a reproducible baseline before optimization.
3. Profile the real workload; separate CPU, allocation, lock, I/O, database, network, and startup costs.
4. Identify the dominant bottleneck and validate it with a focused experiment.
5. Check asymptotic complexity, repeated scans, N+1 calls, serialization, batching, caching, queueing, and contention.
6. Apply the smallest optimization that addresses the measured cause.
7. Re-run correctness and compatibility tests.
8. Benchmark with warm-up, repeated samples, realistic data, controlled environment, and reported variance.
9. Check tail latency, memory, GC, resource leaks, overload behavior, and performance cliffs.
10. State trade-offs such as memory for speed, staleness, complexity, fairness, or startup cost.
11. Reject benchmarks that compare different work, omit warm-up, use tiny unrealistic input, or report only the best run.

## Required report

- Baseline and environment
- Profile evidence
- Change and hypothesis
- Before/after metrics with variance
- Correctness evidence
- Resource and operational trade-offs

## Optional reference

Load `references/benchmark-template.md` for formal before/after performance evidence.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
