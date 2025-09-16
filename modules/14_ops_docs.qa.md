# Module: Ops Docs & Onboarding (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify ops documentation accuracy.

## Checks
- Markdown linter passes.
- Links valid.
- Env vars in docs match code.
- Kill/keep rubric present.

## Pass/Fail Rules
- PASS if all checks satisfied.
- SOFT_FAIL if doc inconsistencies.
- HARD_FAIL if env mismatches or missing docs.

## Output
- `qa_report.json` with status, findings, patches.
