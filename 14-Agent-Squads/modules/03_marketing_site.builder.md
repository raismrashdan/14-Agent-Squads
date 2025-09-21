# Module: Marketing Site (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Scaffold the public marketing site with homepage, pricing, and waitlist pages.

## Context
- Next.js 14, TS strict
- Tailwind + shadcn
- Conditional Plausible analytics
- Waitlist form integration

## Required Changes
- [ ] Create `(marketing)/layout.tsx` with optional Plausible script.
- [ ] Create `(marketing)/page.tsx` with hero, feature grid, testimonial, CTAs.
- [ ] Create `(marketing)/pricing/page.tsx` with 3 tiers.
- [ ] Create `(marketing)/waitlist/page.tsx` embedding `<WaitlistForm />`.
- [ ] Ensure CTAs call `track("JoinWaitlistClicked")` shim.

## Guards
- Analytics only if env var set.
- Accessibility: landmarks, single `<h1>`, labelled controls.
- Images use `next/image` with width/height.
- Australian English copy.

## Output Format
- Unified diff.
- `module_report.json`.
