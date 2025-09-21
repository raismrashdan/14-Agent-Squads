# Module: Design System & Theming (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify design system meets accessibility and theming requirements.

## Checks
- Grep for inline hex values → none should exist.
- Axe-core scan for focus-visible and contrast compliance.
- Verify ThemeProvider correctly switches dark/light.

## Pass/Fail Rules
- PASS if all checks pass.
- SOFT_FAIL if minor styling issues (e.g., missing dark token).
- HARD_FAIL if colour tokens or focus accessibility missing.

## Output
- `qa_report.json` with status, findings, patches.
