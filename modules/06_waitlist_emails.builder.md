# Module: Waitlist Form & Emails (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Implement waitlist form with validation, server action, and welcome email.

## Context
- RHF + Zod for form validation
- Resend + React Email for welcome email
- Event tracking via shim

## Required Changes
- [ ] Add `<WaitlistForm />` client component.
- [ ] Add `submitWaitlist` server action.
- [ ] Insert email into DB via Supabase.
- [ ] Send welcome email if Resend configured.
- [ ] Track `JoinWaitlistSubmitted`.

## Guards
- Zod schema mirrored client + server.
- Duplicate email handled gracefully.
- Server throws error if email envs missing.

## Output Format
- Unified diff.
- `module_report.json`.
