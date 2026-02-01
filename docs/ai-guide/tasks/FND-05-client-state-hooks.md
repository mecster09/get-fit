You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Client State: typed hooks for loading/saving config

## Goal
Implement reusable hooks that connect UI pages to repositories with loading/saving states and minimal caching.

## Dependencies / Prereqs
- FND-04
- FND-02

## Scope (granular checklist)
- [ ] Create hooks: useProfile, useFastingSchedule, useExerciseSchedule, useResistanceSchedule, useWeightEntries
- [ ] Ensure hooks expose: data, loading, error, save/update functions
- [ ] Implement lightweight caching/invalidation so updates reflect across pages
- [ ] Add reusable UI primitives for loading/error states

## Acceptance Criteria (BDD)
- Given I edit config in one page, when I navigate to another page, then updated values are shown without refresh.
- Given a storage error, when it occurs, then the UI shows an actionable error state.

## Implementation Notes
- Prefer React built-ins + minimal utilities; avoid heavy state libraries unless already in repo.
- Avoid calling IndexedDB on every render; use effects and memoization.

## Test Plan & Coverage Requirements
- Add unit tests for hook behavior (mock repositories).
- Add component tests verifying loading->loaded transitions.
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- Reusable typed hooks
- Shared loading/error components
- Automated tests
