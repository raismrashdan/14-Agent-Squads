# Module: SEO & MDX (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify SEO metadata and MDX page.

## Checks
- Static parse of `generateMetadata` includes title + description.
- OG image alt present.
- MDX renders without errors.

## Pass/Fail Rules
- PASS if all checks satisfied.
- SOFT_FAIL if metadata incomplete.
- HARD_FAIL if MDX fails to render.

## Output
- `qa_report.json` with status, findings, patches.
