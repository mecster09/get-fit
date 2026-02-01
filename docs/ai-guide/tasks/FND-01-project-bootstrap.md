You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Project Bootstrap: Next.js + Fastify workspace scaffold

## Goal
Create the foundational application scaffold for a Next.js PWA frontend and a Fastify API, with a clean monorepo/workspace structure and shared TypeScript types.

## Scope (granular checklist)
- [ ] Initialize repository structure (e.g., /apps/web, /apps/api, /packages/shared)
- [ ] Set up TypeScript configs (base + per-package) with path aliases
- [ ] Configure package manager workspaces and scripts (dev, build, test, lint, format)
- [ ] Set up environment variable conventions for web and api (examples + validation)
- [ ] Add minimal shared types package for domain models (Profile, schedules, etc.)
- [ ] Add basic healthcheck endpoints for api and basic landing page for web

## Acceptance Criteria (BDD)
- Given a fresh clone, when I run the documented commands, then web and api start locally without errors.
- Given the shared types package, when imported by web and api, then TypeScript builds successfully.

## Implementation Notes
- Follow Next.js App Router conventions for web.
- Fastify should run independently but share types via /packages/shared.
- Keep it minimal—no premature abstractions.

## Test Plan & Coverage Requirements
- Add a minimal smoke test for api health route.
- Add a minimal page render test for web (component test).
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- Workspace/monorepo scaffold
- Shared TS package
- Working dev scripts for web/api
- README quickstart
