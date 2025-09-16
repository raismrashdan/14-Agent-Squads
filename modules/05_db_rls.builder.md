# Module: Database (Drizzle) & RLS (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Define schema with Drizzle, manage migrations, and enforce RLS policies in SQL.

## Context
- `/lib/db/schema.ts` + `/drizzle/` for Drizzle
- `/sql/0001_init.sql` for RLS/policies
- CI runs Drizzle migrations + applies SQL

## Required Changes
- [ ] Create Drizzle schema for waitlist + profiles.
- [ ] Generate initial migration.
- [ ] Create `/sql/0001_init.sql` for RLS (idempotent).
- [ ] Add migration scripts to package.json.
- [ ] Configure `.github/workflows/migrate.yml`.

## Guards
- All tables defined in Drizzle.
- RLS enforced in `/sql/0001_init.sql`.
- CI fails if `db:gen` produces unstaged changes.

## Output Format
- Unified diff.
- `module_report.json`.
