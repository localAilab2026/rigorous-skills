---
name: rigorous-frontend
description: "Implement, refactor, debug, or review frontend and UI code in web or desktop projects. Use for components, forms, state management, routing, asynchronous data, responsive layouts, accessibility, browser behavior, client security, or frontend tests. Covers complete interaction states rather than only the successful rendered view."
---

# Rigorous Frontend Engineering

Model the full user interaction lifecycle, not only the happy-path screenshot.

## Workflow

1. Inspect framework version, component conventions, state ownership, design system, routing, API clients, tests, and build tooling.
2. Define loading, empty, success, validation, partial, stale, offline, unauthorized, and error states.
3. Define behavior for rapid repeated actions, cancellation, out-of-order responses, navigation, refresh, and component destruction.
4. Keep state ownership explicit and prevent stale writes, subscription leaks, duplicate requests, and hidden global coupling.
5. Preserve keyboard navigation, focus, labels, semantic structure, contrast, screen-reader behavior, and reduced-motion preferences.
6. Handle responsive layout, long text, localization, time zones, number/date formatting, and browser support.
7. Treat rendered content, URLs, storage, and API data as trust boundaries.
8. Implement incrementally using existing patterns; avoid unnecessary framework rewrites.
9. Test behavior through user-observable interactions, not internal component methods.
10. Verify accessibility, network failure, slow responses, repeated clicks, route changes, and cleanup.

## Completion evidence

Include build/type-check/lint, focused component tests, representative integration or browser checks, and visual verification where layout changed.

## Optional reference

Load `references/ui-state-matrix.md` when the feature has asynchronous, validation, authorization, or navigation states.

## Completion discipline

- Report only commands and results actually observed.
- Distinguish verified, partially verified, blocked, and assumed behavior.
- Do not equate compilation, test count, documentation, or code appearance with correctness.
- Do not silently weaken a requirement because it is difficult.
- End with: changed behavior, evidence run, unresolved risks, and exact blockers.
