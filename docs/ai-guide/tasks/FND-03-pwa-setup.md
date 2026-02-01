You are the software engineer implementing this task in the Weight Loss Tracker project.

Tech stack (must match): TypeScript, Next.js (App Router), Fastify API, PWA, IndexedDB, React Icons.

Quality & coverage (required): ship production-quality code with automated tests. Prefer BDD-style acceptance criteria where applicable. Include appropriate coverage across: unit, API/integration, functional, and end-to-end. Add/adjust CI or automation scripts if needed. No flaky tests.

Architecture principles (required): DRY, separation of concerns, KISS. Follow Next.js standards and best practices (routing, data fetching, server/client boundaries, env/config, security). Keep changes minimal, cohesive, and well-documented.

Deliverables: implement the requested feature/fix, update or add tests, and provide brief notes on what changed and how to run/verify.

---

# Task: PWA Setup: manifest, service worker, offline-first basics

## Goal
Enable Progressive Web App capabilities: installable manifest, service worker caching, offline-friendly shell.

## Dependencies / Prereqs
- FND-01
- FND-02

## Scope (granular checklist)
- [ ] Add web manifest (name, icons, theme color, display, start_url)
- [ ] Add/enable service worker strategy suitable for Next.js (cache static assets + app shell)
- [ ] Ensure offline load shows cached shell and helpful offline message
- [ ] Add installability checks (Lighthouse-ready) and document
- [ ] Add app icons placeholders and build pipeline support

## Acceptance Criteria (BDD)
- Given I load the app once, when I go offline and refresh, then I still see a usable app shell or offline page.
- Given supported browsers, when I open the site, then it is installable as a PWA.

## Implementation Notes
- Prefer a well-supported Next.js PWA approach already used in the repo if present; otherwise keep configuration minimal.
- Do not cache API responses unless explicitly designed; start with shell caching only.

## Test Plan & Coverage Requirements
- Add a simple E2E test that validates offline page/shell behavior (as feasible).
- All changes are TypeScript-first, linted, and formatted.
- Add or update automated tests for all new utilities and critical flows.
- Update README with run/test/build instructions.

## Deliverables
- Manifest + icons wired
- Service worker configured
- Offline fallback behavior
- Docs for PWA behavior
