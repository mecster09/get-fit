You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Schedule: This Week 7-day plan view
**Mapped User Story:** US-07

## Goal
Implement Schedule → This Week view showing a 7-day breakdown for fasting, treadmill, and resistance plans.

## Dependencies / Prereqs
- US-06 recommended

## Scope (granular checklist)
- [ ] Add This Week tab/section under Schedule
- [ ] Render 7-day list/grid with day labels and per-activity summaries
- [ ] Ensure fasting exceptions are reflected correctly
- [ ] Add small UI affordance to highlight 'today'
- [ ] Reuse shared selectors/utilities for schedule resolution

## Acceptance Criteria (BDD)
- Given schedules exist, when I open This Week, then I see a 7-day breakdown for each activity.
- Given a fasting exception exists, then that day shows exception times not repeating schedule.

## Implementation Notes
- Compute week start deterministically (e.g., Monday start) and document choice.
- Avoid heavy computations in render loop; precompute week model.
- Keep styling minimal and consistent with existing design system.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add E2E test verifying exception day display.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- This Week view components
- Automated tests
