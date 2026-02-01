You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Tooling & CI: linting, formatting, test runners, automation

## Goal
Ensure the repo has consistent linting/formatting, test runners for unit/component/api, and CI automation.

## Dependencies / Prereqs
- FND-01
- FND-02
- FND-06

## Scope (granular checklist)
- [ ] Configure ESLint + TypeScript rules for Next.js and Node (Fastify)
- [ ] Configure Prettier and consistent formatting scripts
- [ ] Set up unit test runner (Vitest/Jest) for shared/web/api
- [ ] Set up component testing (React Testing Library) for web
- [ ] Set up API testing harness (tap/vitest/supertest) for Fastify
- [ ] Set up Playwright for E2E tests and basic base config
- [ ] Add CI workflow to run lint + unit + component + api + e2e (as appropriate)

## Acceptance Criteria (BDD)
- Given CI runs, when code is pushed, then lint and tests run automatically and fail on regressions.
- Given local dev, when I run npm scripts, then lint/format/test commands work consistently.

## Implementation Notes
- Keep configs shared where possible but avoid coupling web and api rules excessively.
- E2E should be stable and minimal; avoid flaky selectors.

## Test Plan & Coverage Requirements
- Add at least one Playwright smoke test for app routing.
- Add at least one unit test and one API test to prove harness works.
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- ESLint/Prettier config + scripts
- Test harness for unit/component/api/e2e
- CI workflow(s)
- Docs for running tests
