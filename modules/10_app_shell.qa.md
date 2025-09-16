# Module: App Shell (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify app shell renders and protects routes.

## Checks
- Authenticated user sees profile rendered.
- Unauthed → redirected to `/login`.
- Bundle size check within budget.

## Pass/Fail Rules
- PASS if all checks satisfied.
- HARD_FAIL if auth bypass or SSR fetch fails.

## Output
- `qa_report.json` with status, findings, patches.
