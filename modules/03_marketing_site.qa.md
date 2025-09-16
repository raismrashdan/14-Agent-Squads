# Module: Marketing Site (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify marketing site is implemented correctly.

## Checks
- `/` renders hero H1 and CTA.
- Pricing page shows 3 cards.
- Waitlist page embeds form.
- Plausible only loads with env var.
- Axe-core scan for headings/landmarks.
- Images sized correctly (CLS budget).

## Pass/Fail Rules
- PASS if all checks satisfied.
- SOFT_FAIL if fixable issues (alt text missing).
- HARD_FAIL if systemic issues (analytics always injected, layout broken).

## Output
- `qa_report.json` with status, findings, patches.
