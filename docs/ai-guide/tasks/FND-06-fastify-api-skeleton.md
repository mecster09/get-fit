You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Fastify API: baseline server, plugins, and route structure

## Goal
Create a Fastify API skeleton with a clean plugin/route structure, validation, and health endpoints.

## Dependencies / Prereqs
- FND-01

## Scope (granular checklist)
- [ ] Set up Fastify server entrypoint with sensible defaults (logging, cors as needed)
- [ ] Create route modules structure (e.g., /routes, /plugins)
- [ ] Add /health and /version endpoints
- [ ] Add request/response validation strategy (zod/json-schema)
- [ ] Add basic error handling and consistent response shape

## Acceptance Criteria (BDD)
- Given api is running, when I hit /health, then I receive a 200 with status ok.
- Given invalid payloads, when sent to validated routes, then api returns a clear 4xx with error details.

## Implementation Notes
- Keep API minimal until a real remote feature requires it; avoid duplicating local storage features.
- If shared validation schemas exist, colocate them with shared types or in api.

## Test Plan & Coverage Requirements
- Add API tests for /health and one validated sample route.
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- Fastify server skeleton
- Validation + error handling
- API tests + docs
