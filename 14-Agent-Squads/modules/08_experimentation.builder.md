# Module: Experimentation (Builder)

## Capabilities
- experimentation: true
- observability: false
- security_headers: false

## Goal
Implement deterministic A/B testing primitives for marketing and app experiences.

## Context
- Assignment: salted hash by user_id or cookie.
- Exposure: one-time event log.
- Outcomes: track waitlist and auth funnel events.
- Integration with Plausible if enabled.

## Required Changes
- [ ] Add `/lib/exp/assign.ts` for bucketing.
- [ ] Add `/lib/exp/client.ts` and `/lib/exp/server.ts` for exposure logging.
- [ ] Create `/lib/exp/flags.ts` with typed config.
- [ ] Update CTAs and waitlist form to call `track()` with experiment/variant context.

## Guards
- Assignment is stable and deterministic.
- One exposure event per subject.
- No PII in payloads.
- Experiments disable gracefully if env vars missing.

## Output Format
- Unified diff.
- `module_report.json`.
