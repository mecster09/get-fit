You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Resistance Config: sets/exercises/reps weekly plan
**Mapped User Story:** US-05

## Goal
Enable weekly resistance training plan by day with structure: X sets, Y exercises per set, Z reps.

## Scope (granular checklist)
- [ ] Define ResistanceSchedule model: map weekday -> session {sets, exercisesPerSet, reps}
- [ ] Implement Config → Resistance UI to add/edit/remove session per day
- [ ] Persist resistance schedule to IndexedDB
- [ ] Create selector utility: getResistanceSession(date) returning null when not scheduled
- [ ] Render a concise summary in Today and This Week (e.g., '3 sets • 4 exercises/set • 10 reps')

## Acceptance Criteria (BDD)
- Given I define sets, exercises per set, and reps for a day and save, then summary appears for that day.
- Given invalid inputs, when I save, then validation errors display and saving is blocked.

## Implementation Notes
- Validation: sets>=1, exercisesPerSet>=1, reps>=1; all integers.
- Use shared numeric input component with consistent error messages.
- Keep domain calculations in utilities (not in components).

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add tests for validation and summary formatting.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Resistance schedule UI + persistence
- Selectors and summary formatting + tests
