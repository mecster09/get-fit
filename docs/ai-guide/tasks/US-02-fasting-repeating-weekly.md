You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Fasting Config: create repeating weekly eating window
**Mapped User Story:** US-02

## Goal
Allow user to define a repeating weekly eating window for all days and persist it.

## Dependencies / Prereqs
- US-01 recommended (profile not strictly required)

## Scope (granular checklist)
- [ ] Define FastingSchedule types: repeatingWindow + per-day overrides container (even if overrides not used yet)
- [ ] Implement Config → Fasting UI to set start/end time and apply to selected days (Mon–Sun, default all)
- [ ] Persist fasting schedule to IndexedDB and load reliably
- [ ] Create schedule computation utility: getEffectiveFastingWindow(date)
- [ ] Render fasting schedule in Schedule views if they exist; otherwise add minimal adapters/hooks

## Acceptance Criteria (BDD)
- Given I set a repeating schedule for all days and save, then it persists and appears in Today and This Week.
- Given I reopen Config, then times and selected days are shown accurately.

## Implementation Notes
- Store times in a canonical format (e.g., minutes from midnight) to avoid locale/timezone pitfalls.
- Guard against invalid windows (end <= start) unless you explicitly support crossing midnight; document behavior.
- Avoid duplicating logic between Today and This Week—use shared selectors/utilities.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add unit tests for getEffectiveFastingWindow across weekdays.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Fasting repeating schedule UI + persistence
- Shared schedule selector utilities
- Automated tests and notes
