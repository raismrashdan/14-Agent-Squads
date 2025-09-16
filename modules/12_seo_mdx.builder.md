# Module: SEO & MDX (Builder)

## Capabilities
- experimentation: false
- observability: false
- security_headers: false

## Goal
Add SEO defaults and MDX docs page.

## Context
- Next.js metadata API
- `/content/docs.mdx`

## Required Changes
- [ ] Implement `seo.ts` for defaults.
- [ ] Add Open Graph metadata.
- [ ] Add `/content/docs.mdx` page.

## Guards
- Title/description always present.
- OG image has alt text.
- MDX renders at build.

## Output Format
- Unified diff.
- `module_report.json`.
