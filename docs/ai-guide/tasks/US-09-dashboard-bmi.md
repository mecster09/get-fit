You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Dashboard: BMI calculation and display
**Mapped User Story:** US-09

## Goal
Display current BMI using the standard BMI formula and update when inputs change.

## Dependencies / Prereqs
- US-01
- US-08 recommended

## Scope (granular checklist)
- [ ] Confirm required inputs exist for BMI (likely height needed). If height missing in profile, implement minimal height field in Config/Profile
- [ ] Add BMI calculation utility with documented formula and units
- [ ] Display BMI value on dashboard with appropriate rounding
- [ ] Handle missing inputs by showing 'BMI unavailable' with link to Config

## Acceptance Criteria (BDD)
- Given required inputs, when I open dashboard, then BMI is shown and updates when inputs change.
- Given BMI inputs missing, when I open dashboard, then BMI is unavailable with guidance.

## Implementation Notes
- If adding height: store in cm; convert to meters for BMI (kg / m^2).
- Validate height range sensibly (e.g., 50–250 cm) and weight range (kg).
- Keep BMI logic pure and unit-tested.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add tests for BMI formula and missing-input behavior.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Profile height field (if needed) + persistence migration
- BMI display on dashboard
- Automated tests
