You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Profile Config: create/edit user profile (sex, age, weights)
**Mapped User Story:** US-01

## Goal
Implement profile capture/editing in Config and persist it locally so downstream features (dashboard, schedules) can use it.

## Scope (granular checklist)
- [ ] Create a typed Profile model (sex, age, currentWeight, targetWeight) with validation constraints
- [ ] Implement Config → Profile UI form with controlled inputs and inline validation
- [ ] Persist profile to IndexedDB and load on app start / when opening Config
- [ ] Expose profile access via a single data access layer (SoC) used by UI and computations
- [ ] Add optimistic UI save state + error handling (toasts or inline)
- [ ] Wire profile updates to re-render dependent dashboard calculations (if dashboard exists)

## Acceptance Criteria (BDD)
- Given I open Config, when I enter Sex, Age, Current Weight and Target Weight and save, then values persist and are shown on return.
- Given saved values, when I update any field and save, then values persist and dependent calculations re-run.
- Given invalid values, when I try to save, then errors display and saving is blocked.

## Implementation Notes
- Use Next.js App Router conventions; keep form UI in a client component.
- Use IndexedDB wrapper (e.g., idb) if present; otherwise add a minimal typed wrapper (no over-engineering).
- Keep all persistence logic out of components (repository/service module).
- Store weights with explicit unit (kg) and document assumptions.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add persistence tests around the repository using fake-indexeddb.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Profile form UI in Config section
- IndexedDB persistence + typed repository
- Automated tests (unit + component + E2E)
- Dev notes: how to run tests + any migrations
