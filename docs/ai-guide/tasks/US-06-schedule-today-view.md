You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Schedule: Today view summary
**Mapped User Story:** US-06

## Goal
Implement Schedule → Today view that shows today's fasting window (with exceptions), treadmill minutes, and resistance summary.

## Dependencies / Prereqs
- US-02/03/04/05 selectors available or implemented concurrently

## Scope (granular checklist)
- [ ] Create Schedule section route/page with Today tab/section
- [ ] Implement Today view UI that pulls effective schedules for 'today'
- [ ] Display clear 'Not scheduled' states per activity
- [ ] Ensure fast re-render on schedule edits (use hooks/store)
- [ ] Add basic empty-state guidance links to Config sections

## Acceptance Criteria (BDD)
- Given schedules exist, when I open Today, then today's fasting/exercise/resistance are displayed.
- Given an activity is not scheduled today, then it displays 'Not scheduled'.

## Implementation Notes
- Derive 'today' using user locale/timezone safely; avoid server-side date mismatch (client-only date for view).
- Keep computations in selector utilities shared with This Week.
- Ensure responsive layout (mobile-first PWA).

## Test Plan & Coverage Requirements
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add E2E test: configure schedules -> Today shows expected content.
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.

## Deliverables
- Today view page/components
- Tests (component + E2E)
