---
name: rigorous-devops
description: "Implement, debug, or review builds, CI/CD, containers, deployment scripts, infrastructure configuration, environment management, observability, health checks, rollouts, backups, or production operations. Use for Docker, Kubernetes, pipelines, system services, cloud infrastructure, release failures, and environment-specific behavior."
---

# Rigorous DevOps and Delivery

Make builds and deployments reproducible, repeatable, observable, and recoverable.

## Workflow

1. Inspect repository build tools, lockfiles, runtime versions, existing pipelines, deployment targets, secrets handling, and environment assumptions.
2. Reproduce the failure or baseline locally/in an equivalent environment when possible.
3. Pin versions and inputs needed for deterministic builds; avoid hidden machine state.
4. Separate build-time and runtime configuration; validate required variables without exposing secrets.
5. Make provisioning and deployment idempotent and safe to rerun.
6. Define startup, readiness, liveness, graceful shutdown, dependency failure, and rollback behavior.
7. Model failure during every rollout phase and mixed-version compatibility.
8. Protect persistent data with backup, restore, migration, and disaster-recovery plans appropriate to the change.
9. Set resource limits and check disk, memory, CPU, file descriptors, networks, permissions, and storage ownership.
10. Add actionable logs, metrics, traces, and health signals without leaking secrets.
11. Test clean environment setup, repeated deployment, failed deployment, rollback, restart, and upgrade.
12. Record exact commands, versions, and environmental blockers.

## Prohibitions

- Do not solve permission problems with broad insecure privileges by default.
- Do not use unpinned mutable tags for reproducible production deployment.
- Do not claim rollback safety without testing data and version compatibility.

## Optional reference

Load `references/delivery-checklist.md` for deployment, rollout, or production-readiness work.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
