You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: Web App Shell: layout, navigation, and routes

## Goal
Create the foundational Next.js UI shell with navigation to Config, Schedule (Today/This Week), and Dashboard.

## Dependencies / Prereqs
- FND-01

## Scope (granular checklist)
- [ ] Create App Router routes: /dashboard, /schedule/today, /schedule/week, /config
- [ ] Implement a shared layout with minimal navigation (bottom nav for mobile + header)
- [ ] Add placeholders for each page with consistent headings and empty states
- [ ] Add React Icons usage for nav items
- [ ] Ensure responsive, PWA-friendly layout (safe areas, tap targets)

## Acceptance Criteria (BDD)
- Given I open the app, when I navigate between Dashboard, Schedule Today/This Week, and Config, then routing works without full page reload issues.
- Given mobile viewport, when I use navigation, then tap targets are accessible and visible.

## Implementation Notes
- Keep shell components as client components only when needed.
- Avoid adding global state prematurely—just routing + layout.

## Test Plan & Coverage Requirements
- Add basic navigation E2E test covering all routes.
- Add component tests for the nav shell rendering.
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- Next.js routes + app shell
- Navigation with React Icons
- Automated tests
