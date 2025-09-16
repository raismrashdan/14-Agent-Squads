# Module: Testing & CI (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify CI pipelines enforce quality gates.

## Checks
- Lint workflow passes.
- Playwright e2e workflows pass.
- Migration workflow applies cleanly.
- `db:gen` produces no unstaged changes.

## Pass/Fail Rules
- PASS if all checks satisfied.
- HARD_FAIL if CI workflows fail.

## Output
- `qa_report.json` with status, findings, patches.
