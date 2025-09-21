# Module: Emails (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Set up a dedicated email module for transactional messages using Resend + React Email.

## Context
- React Email templates in `/emails/`
- Resend server action wrapper
- Uses `RESEND_API_KEY` and `EMAIL_FROM`

## Required Changes
- [ ] Create `emails/welcome.tsx` React Email template.
- [ ] Add `sendWelcome(to: string)` server action in `/lib/email.ts`.
- [ ] Fail-fast if required env vars missing.
- [ ] Ensure no secrets appear in client code.
- [ ] Add tests for rendering email templates.

## Guards
- Inline CSS only, no external styles.
- Templates render consistently in major email clients.
- No secrets or PII in templates.

## Output Format
- Unified diff.
- `module_report.json`.
