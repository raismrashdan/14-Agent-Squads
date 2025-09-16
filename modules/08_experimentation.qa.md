# Module: Experimentation (QA)

## Capabilities
- experimentation: true
- observability: false
- security_headers: false

## Purpose
Verify experiments are assigned and tracked correctly.

## Checks
- Same subject → same variant.
- Exposure event fires once only.
- Payload excludes PII.
- SRM sanity: variant split ≈ expected.

## Pass/Fail Rules
- PASS if all checks satisfied.
- SOFT_FAIL if small fixable issues (e.g. extra exposure).
- HARD_FAIL if determinism or privacy fails.

## Output
- `qa_report.json` with status, findings, patches.
