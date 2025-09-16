# Module: Database (Drizzle) & RLS (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify DB schema and RLS policies are correctly implemented.

## Checks
- Apply Drizzle migrations successfully.
- Run `/sql/0001_init.sql` idempotently.
- Verify RLS blocks unauthenticated access.
- Run smoke query with Drizzle client.

## Pass/Fail Rules
- PASS if all checks satisfied.
- HARD_FAIL if migrations fail or RLS missing.

## Output
- `qa_report.json` with status, findings, patches.
