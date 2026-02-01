You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Dashboard: progress to target weight
**Mapped User Story:** US-08

## Goal
Show progress toward target weight using saved profile (and latest weight if weight logging exists).

## Dependencies / Prereqs
- US-01

## Scope (granular checklist)
- [ ] Create/extend Dashboard route/page and basic layout
- [ ] Implement progress metric: amount remaining and percent-to-target (define clearly)
- [ ] Use Profile currentWeight/targetWeight (or latest weight entry if US-11 implemented)
- [ ] Handle missing data gracefully with prompts to complete Config

## Acceptance Criteria (BDD)
- Given current weight and target are saved, when I open dashboard, then progress is displayed and computed correctly.
- Given current weight changes, when I open dashboard, then progress updates.

## Implementation Notes
- Create a dashboard view model selector that centralizes calculations.
- Keep formatting consistent (units, rounding).
- Avoid server rendering mismatch for client-side stored values (dashboard is likely client component).

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add tests for progress calculation and missing-data states.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Dashboard progress card/widget
- Tests + notes
