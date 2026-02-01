You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Weight Logging: record weight entries over time
**Mapped User Story:** US-11

## Goal
Enable users to log weight (date + weight), persist entries, and expose them to the dashboard for trends.

## Dependencies / Prereqs
- US-01 recommended

## Scope (granular checklist)
- [ ] Define WeightEntry model: {dateISO, weightKg} and repository in IndexedDB
- [ ] Create UI to add a new weight entry (default date=today) and list recent entries
- [ ] Allow editing/deleting an entry (optional but recommended) with confirmation
- [ ] Define 'current weight' source of truth (latest entry vs profile) and implement selector logic
- [ ] Ensure dashboard uses latest entry when available

## Acceptance Criteria (BDD)
- Given I add a weight entry and save, then it persists and appears in the list.
- Given multiple entries, dashboard trend uses them (or is prepared to).

## Implementation Notes
- Store date as ISO string (YYYY-MM-DD) to avoid timezone drift.
- If editing/deleting: keep operations atomic in repository.
- Keep UI minimal: list + add form; no over-design.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add/extend Playwright E2E tests for the primary user flows covered in this task.
- Add repository tests using fake-indexeddb for CRUD.

## Deliverables
- Weight logging UI + persistence
- Selectors for latest weight
- Automated tests
