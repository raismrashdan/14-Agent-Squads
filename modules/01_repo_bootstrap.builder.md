# Module: Repo Bootstrap (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Set up the foundational repository scaffold with Next.js, Supabase, TypeScript strict mode, Tailwind, shadcn, pnpm, Biome, and Playwright.

## Context
- Framework: Next.js 14 App Router
- Hosting: Vercel
- Auth & DB: Supabase
- Tooling: Biome for lint/format, Playwright for e2e smoke tests
- Package manager: pnpm
- UI: Tailwind + shadcn (Radix primitives copied into repo)

## Required Changes
- [ ] Initialise Next.js project with App Router and TS strict.
- [ ] Add Tailwind with HSL tokens in `/styles/globals.css`.
- [ ] Install shadcn components locally under `/components/ui`.
- [ ] Configure pnpm, `.gitignore`, and `.devcontainer`.
- [ ] Add Biome config (`biome.json`).
- [ ] Add Playwright setup (`playwright.config.ts`).
- [ ] Add GitHub Actions workflows for lint/e2e/migrate.
- [ ] Ensure `tsconfig.json` has `"strict": true`.

## Guards
- No unused dependencies installed.
- Strict TypeScript (no `any`).
- shadcn components must be copied locally, not imported from npm.
- No server envs exposed in client bundles.

## Output Format
- Unified diff of all created/modified files.
- `module_report.json` with: files_changed[], decisions[], TODOs[], risk_flags[].
