# Module: Observability (QA)

## Capabilities
- experimentation: true
- observability: true
- security_headers: false

## Purpose
Verify observability primitives.

## Checks
- Logger adds request IDs.
- Event sink writable.
- `/healthz` returns 200 JSON.
- Logs contain no PII.

## Pass/Fail Rules
- PASS if all checks satisfied.
- HARD_FAIL if logs leak PII.

## Output
- `qa_report.json` with status, findings, patches.
