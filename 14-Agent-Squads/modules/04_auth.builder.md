# Module: Auth (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Implement Supabase magic link authentication with protected routes.

## Context
- `/login/page.tsx` for login form
- Supabase server/client helpers
- Protected `(app)` group

## Required Changes
- [ ] Add login page with email magic link.
- [ ] Add Supabase helpers in `/lib/supabase/`.
- [ ] Create `requireUser()` in `/lib/auth.ts`.
- [ ] Protect `(app)` routes with requireUser.
- [ ] Add `signOut` server action.

## Guards
- Never expose `SUPABASE_SERVICE_ROLE`.
- Server-only envs validated at runtime.
- Redirect unauthenticated users → `/login`.

## Output Format
- Unified diff.
- `module_report.json`.
