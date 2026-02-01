You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Dashboard: weight trend and estimated timeline to target
**Mapped User Story:** US-10

## Goal
Show a weight-loss trend and estimate time-to-target based on observed rate of change, with safeguards for insufficient data.

## Dependencies / Prereqs
- US-11 strongly recommended

## Scope (granular checklist)
- [ ] Define data requirements (e.g., minimum 2–3 weight entries across >=7 days) for a trend estimate
- [ ] Implement trend calculation utility (e.g., linear regression or simple delta/time) with clear assumptions
- [ ] Compute estimated date/time-to-target using current rate; clamp/guard unrealistic rates (avoid misleading output)
- [ ] Render trend visualization (simple sparkline or line chart) and estimated timeline text
- [ ] Show 'need more data' message when insufficient entries exist

## Acceptance Criteria (BDD)
- Given multiple weight entries, when I open dashboard, then trend and estimated timeline are shown based on observed progression.
- Given insufficient data, when I open dashboard, then no estimate is shown and a clear message explains what's needed.

## Implementation Notes
- Prefer simple, explainable math over complex models; document assumptions in code comments.
- Use client-side only charting consistent with existing stack; keep it lightweight.
- Ensure all computations are deterministic and unit-tested.

## Test Plan & Coverage Requirements
- Add/extend unit tests (Vitest/Jest whichever is in-repo) for all pure logic and validation rules.
- Add/extend functional/component tests for key UI behavior (e.g., React Testing Library).
- Add tests for insufficient data gating and reasonable estimates.
- Add/extend Playwright E2E tests for the primary user flows covered in this task.

## Deliverables
- Trend + timeline widgets on dashboard
- Calculation utilities + tests
