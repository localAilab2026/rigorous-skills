# OpenCode Rigorous Engineering Suite

This bundle contains independently loadable programming skills. Install the skill folders directly under either:

```text
<project>/.opencode/skills/
```

or globally:

```text
~/.config/opencode/skills/
```

Do not place the outer `skills` folder inside another skill folder. The resulting layout should look like:

```text
.opencode/skills/
  rigorous-feature/SKILL.md
  rigorous-debugging/SKILL.md
  rigorous-testing/SKILL.md
  ...
```

OpenCode can select the narrowest matching skill from its description, so it does not need to load one large universal instruction file.

## Included skills

| Folder | Purpose |
|---|---|
| `rigorous-specification` | Turn requests into testable engineering contracts |
| `rigorous-feature` | Implement complete repository-aware features |
| `rigorous-debugging` | Reproduce, isolate, and fix root causes |
| `rigorous-testing` | Design tests that can disprove implementations |
| `rigorous-code-review` | Audit code as untrusted evidence |
| `rigorous-refactoring` | Change structure without accidental behavior drift |
| `rigorous-api` | Build and review reliable HTTP APIs and clients |
| `rigorous-frontend` | Build resilient accessible user interfaces |
| `rigorous-data` | Protect data integrity across storage and processing |
| `rigorous-concurrency` | Prove thread-safe and asynchronous behavior |
| `rigorous-distributed` | Handle retries, duplicates, messaging, and partial failure |
| `rigorous-security` | Threat-model and harden software changes |
| `rigorous-performance` | Profile and optimize without breaking correctness |
| `rigorous-devops` | Build reproducible safe deployment workflows |

## Selection guidance

- Use the most specific skill matching the requested work.
- Use `rigorous-feature` only when no specialized skill fits better.
- Use `rigorous-specification` when the requested output is a plan or acceptance contract rather than code.
- For combined work, invoke only the few skills that materially apply. Example: a transactional REST endpoint may use `rigorous-api` plus `rigorous-data`; a race-condition audit may use `rigorous-concurrency` plus `rigorous-code-review`.

## Example prompts

```text
Use rigorous-debugging to reproduce and fix this intermittent failure. Do not patch symptoms; add a regression test.
```

```text
Use rigorous-code-review and rigorous-concurrency to audit this implementation. Treat its README and tests as untrusted claims.
```

```text
Use rigorous-feature to implement this request completely in the existing project conventions, then perform an independent auditor pass.
```
