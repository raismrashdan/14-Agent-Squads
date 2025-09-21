# Module: Emails (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify email templates and sending logic.

## Checks
- Render `emails/welcome.tsx` → valid HTML output.
- Validate alt text for all images.
- Ensure no `RESEND_API_KEY` leaks to client.
- Sending fails fast if env vars missing.

## Pass/Fail Rules
- PASS if all checks satisfied.
- SOFT_FAIL if small issues (e.g. missing alt).
- HARD_FAIL if secrets exposed or emails silently fail.

## Output
- `qa_report.json` with status, findings, patches.
