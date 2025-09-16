# Module: Observability (Builder)

## Capabilities
- experimentation: true
- observability: true
- security_headers: false

## Goal
Add minimal observability: request IDs, logs, event sink, `/healthz`.

## Context
- Request ID middleware
- Server logger
- Experiment-aware event sink

## Required Changes
- [ ] Add `/lib/logger.ts` with request IDs.
- [ ] Create server event sink writing JSON lines.
- [ ] Add `/healthz` route for status checks.
- [ ] Ensure no PII in logs.

## Guards
- Logs off in client bundle.
- No PII captured.
- `/healthz` returns 200 with JSON.

## Output Format
- Unified diff.
- `module_report.json`.
