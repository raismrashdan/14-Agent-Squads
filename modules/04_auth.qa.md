# Module: Auth (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify Supabase authentication works and is secure.

## Checks
- Visit `/app/dashboard` unauthenticated → redirected to `/login`.
- Login form requests magic link via Supabase.
- Ensure no `SUPABASE_SERVICE_ROLE` in client bundle.
- Authenticated user sees dashboard.

## Pass/Fail Rules
- PASS if all checks satisfied.
- HARD_FAIL if secrets exposed or auth bypass.

## Output
- `qa_report.json` with status, findings, patches.
