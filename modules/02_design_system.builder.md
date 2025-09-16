# Module: Design System & Theming (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Implement a themeable, accessible design system with HSL tokens, Tailwind, shadcn, and dark mode.

## Context
- Tailwind config in `/tailwind.config.ts`
- ThemeProvider from next-themes
- shadcn primitives for UI components

## Required Changes
- [ ] Define HSL variables in `/styles/globals.css` for light/dark.
- [ ] Add `ThemeProvider` in `/components/theme-provider.tsx`.
- [ ] Configure Tailwind with tokens.
- [ ] Install shadcn primitives into `/components/ui/`.

## Guards
- All colours must reference CSS vars, not inline hex.
- Accessible focus-visible styles for interactive elements.
- Dark mode toggle works correctly.

## Output Format
- Unified diff of file changes.
- `module_report.json` with changes, decisions, TODOs, risk_flags.
