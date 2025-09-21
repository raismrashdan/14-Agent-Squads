# Module: App Shell (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Implement the gated application shell with SSR profile fetch.

## Context
- `(app)/layout.tsx` with sidebar + topbar
- SSR profile load from Supabase
- Sign out action

## Required Changes
- [ ] Add dashboard layout with sidebar (Inbox, Contacts, Settings).
- [ ] Fetch profile server-side in `dashboard/page.tsx`.
- [ ] Add `signOut` button in topbar.

## Guards
- SSR fetch must succeed.
- Client code only where interactive.
- No `any` in TS.

## Output Format
- Unified diff.
- `module_report.json`.
