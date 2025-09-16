# Module: Waitlist Form & Emails (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify waitlist and emails behave correctly.

## Checks
- Valid email inserts into DB and sends welcome email.
- Duplicate email returns friendly error.
- If email env missing, server throws helpful error.
- Track event fired on submit.

## Pass/Fail Rules
- PASS if all checks satisfied.
- SOFT_FAIL if minor error handling missing.
- HARD_FAIL if DB insert/email fails.

## Output
- `qa_report.json` with status, findings, patches.
