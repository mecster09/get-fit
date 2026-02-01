You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Fasting Config: add per-day exception override
**Mapped User Story:** US-03

## Goal
Support exception days that override the repeating fasting schedule for a specific day.

## Dependencies / Prereqs
- US-02

## Scope (granular checklist)
- [ ] Extend FastingSchedule model to support optional per-day override window
- [ ] Update Config → Fasting UI to add/edit/remove an exception for a chosen day
- [ ] Update getEffectiveFastingWindow(date) to prefer override when present
- [ ] Update Schedule Today/This Week rendering to visibly distinguish exception vs repeating schedule (e.g., badge)

## Acceptance Criteria (BDD)
- Given a repeating schedule, when I set an override for a day and save, then only that day is overridden.
- Given an override exists, when I remove it and save, then that day reverts to the repeating schedule.

## Implementation Notes
- Keep override representation minimal: map weekday -> window | null.
- Ensure UI state doesn't accidentally apply override across multiple days.
- Include accessibility: labels and keyboard navigation for day pickers.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add unit tests for override precedence and remove behavior.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Exception-day UI + persistence updates
- Updated schedule utilities + tests
