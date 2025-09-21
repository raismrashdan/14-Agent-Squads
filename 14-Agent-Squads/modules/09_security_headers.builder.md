# Module: Security & Headers (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: true

## Goal
Harden HTTP responses with security headers and rate limiting.

## Context
- CSP, Referrer-Policy, X-Content-Type-Options
- Rate-limit waitlist route

## Required Changes
- [ ] Add Next.js middleware for headers.
- [ ] Configure minimal CSP for Supabase + analytics.
- [ ] Add rate limit middleware for `/api/waitlist`.

## Guards
- No `unsafe-inline` in CSP except hashed styles.
- connect-src allows Supabase/analytics only.
- Friendly error on rate-limit exceeded.

## Output Format
- Unified diff.
- `module_report.json`.
