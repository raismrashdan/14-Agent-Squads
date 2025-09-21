# Module: Testing & CI (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Set up Biome lint, Playwright e2e, and Drizzle migration CI.

## Context
- GitHub Actions workflows under `.github/workflows/`
- Biome for lint/format
- Playwright for smoke tests
- Migration job for Drizzle + SQL

## Required Changes
- [ ] Add `lint.yml` running Biome.
- [ ] Add `e2e.yml` running Playwright.
- [ ] Add `migrate.yml` applying Drizzle + SQL.
- [ ] Add npm scripts for format, lint, e2e.

## Guards
- CI must be green on fresh fork.
- `db:gen` must produce no diffs.
- Tests must run headless in CI.

## Output Format
- Unified diff.
- `module_report.json`.
