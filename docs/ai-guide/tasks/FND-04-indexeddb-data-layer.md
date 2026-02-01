You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Local Persistence Foundation: IndexedDB wrapper + repositories

## Goal
Create a minimal, typed IndexedDB layer and repository pattern to store profile, schedules, and weight entries locally.

## Dependencies / Prereqs
- FND-01

## Scope (granular checklist)
- [ ] Choose/confirm IndexedDB helper (idb) or implement minimal wrapper
- [ ] Define database schema versioning and migration strategy
- [ ] Implement repositories: profileRepo, fastingRepo, exerciseRepo, resistanceRepo, weightRepo (CRUD stubs ok)
- [ ] Add a single 'data access' module exporting typed hooks/selectors for UI usage
- [ ] Add error handling strategy (e.g., return Result types or throw with boundary)

## Acceptance Criteria (BDD)
- Given I save and reload the app, when I read from repositories, then persisted values return correctly.
- Given schema updates, when version increments, then migrations preserve existing data.

## Implementation Notes
- Keep repositories small and domain-focused; do not leak IndexedDB details into UI.
- Use ISO dates for entries; store times as minutes-from-midnight where appropriate.

## Test Plan & Coverage Requirements
- Add repository unit tests using fake-indexeddb.
- Add a migration test covering a version bump scenario.
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- IndexedDB wrapper + schema
- Typed repositories
- Tests for CRUD + migrations
