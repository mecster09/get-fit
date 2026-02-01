You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Exercise Config: treadmill minutes per weekday
**Mapped User Story:** US-04

## Goal
Enable weekly treadmill scheduling (minutes on selected days) and show it in Today and This Week.

## Dependencies / Prereqs
- US-06/US-07 rendering layer may be stubbed if not implemented yet

## Scope (granular checklist)
- [ ] Define ExerciseSchedule model: map weekday -> treadmillMinutes (number | null)
- [ ] Implement Config → Exercise UI for selecting days and entering minutes per day
- [ ] Persist exercise schedule to IndexedDB
- [ ] Create selector utility: getTreadmillMinutes(date)
- [ ] Render treadmill plan in Today and This Week

## Acceptance Criteria (BDD)
- Given I select days and set treadmill minutes and save, then schedule persists and appears in Today/This Week.
- Given minutes removed or set to 0, then that day is not scheduled.

## Implementation Notes
- Normalize minutes: integer >= 1, treat 0/empty as unscheduled.
- Prefer a compact UI (week grid) to avoid repetitive forms.
- Avoid coupling UI to storage schema—use a repository and domain model.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add tests for normalization rules (0/empty).
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Exercise schedule UI + persistence
- Schedule selectors + tests
