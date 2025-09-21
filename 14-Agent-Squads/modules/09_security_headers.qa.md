# Module: Security & Headers (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: true

## Purpose
Verify security headers and rate-limiting.

## Checks
- `/` and `/api/*` responses include expected headers.
- CSP validated with online tool.
- Rate limit triggers after threshold.

## Pass/Fail Rules
- PASS if all checks satisfied.
- HARD_FAIL if headers missing or overly permissive.

## Output
- `qa_report.json` with status, findings, patches.
