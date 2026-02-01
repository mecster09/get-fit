You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: App Reliability: error boundary, logging, and diagnostics

## Goal
Add foundational error boundaries and lightweight logging/diagnostics suitable for a PWA.

## Dependencies / Prereqs
- FND-02

## Scope (granular checklist)
- [ ] Add global error boundary for client-rendered pages
- [ ] Add per-page error UI for Config/Schedule/Dashboard where needed
- [ ] Add a minimal logging utility (console + structured, with env guard)
- [ ] Add user-friendly 'Something went wrong' fallback with reset/retry

## Acceptance Criteria (BDD)
- Given a runtime error occurs, when it happens, then the app shows a friendly error UI and remains navigable.
- Given recoverable errors, when user retries, then the page can reload state.

## Implementation Notes
- Do not log sensitive information.
- Keep logging interface minimal and injectable.

## Test Plan & Coverage Requirements
- Add component test that triggers error boundary and asserts fallback UI.
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- Error boundary + fallback pages
- Logging utility
- Automated tests
