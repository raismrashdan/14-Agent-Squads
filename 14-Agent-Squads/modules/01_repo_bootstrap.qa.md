# Module: Repo Bootstrap (QA)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Purpose
Verify foundational repo setup adheres to guards and acceptance criteria.

## Checks
- Run `pnpm build` succeeds.
- Run `pnpm lint` passes with Biome.
- Run `pnpm test:e2e` executes Playwright smoke tests.
- Ensure shadcn components are copied into `/components/ui`.
- Search client bundle for any server env keys.

## Pass/Fail Rules
- PASS if all checks satisfied.
- SOFT_FAIL if small issues (e.g., unused deps).
- HARD_FAIL if build/lint/tests fail or secrets exposed.

## Output
- `qa_report.json` with status, findings[], patches[] (if SOFT_FAIL).
