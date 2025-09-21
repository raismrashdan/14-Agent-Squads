# Repository Guidelines

## Project Structure & Module Organization
- Root layout:
  - `globals/` – shared rules and expectations: `style_guide.md`, `guardrails.md`, `acceptance_criteria.md`.
  - `modules/` – work packets. Naming: `NN_topic.role.md` (e.g., `04_auth.builder.md`, `04_auth.qa.md`). Keep two‑digit prefixes to preserve order.
  - `runners/` – planning and orchestration artifacts (e.g., `plan.md`).
- When adding a module, provide both builder and QA perspectives and keep scope laser‑focused to the topic.

## Build, Test, and Development Commands
- This repository is Markdown‑first; no build is required.
- Recommended local checks (optional):
  - `npx markdownlint .` – lint Markdown style.
  - `npx markdown-link-check -q modules/**/*.md` – verify links.
- Preview docs in your editor or a Markdown previewer; keep lines readable (~100–120 chars).

## Coding Style & Naming Conventions
- Follow `globals/style_guide.md` (TypeScript strictness, AU English spelling, CSS variable use) when writing code examples.
- File naming: `NN_slug.role.md` using kebab‑case slugs; roles are `builder` or `qa`.
- Tone: concise, instructional, and actionable. Prefer lists and short paragraphs.

## Testing Guidelines
- Treat `globals/acceptance_criteria.md` as the source of truth for outcomes; ensure each relevant module references and satisfies these.
- Cross‑check against `globals/guardrails.md` (secrets, RLS, accessibility, analytics gating).
- For docs quality: run Markdown lint/link checks (above) and validate cross‑references between paired `builder`/`qa` files.

## Commit & Pull Request Guidelines
- Use Conventional Commits:
  - `feat(modules): add 10_app_shell.builder`  
  - `docs(globals): clarify guardrails around analytics`
- PRs must include: purpose, scope of files changed, links to related issues, and screenshots for visual docs/code snippets when helpful.
- Ensure PRs note which acceptance criteria are addressed and how they’re verified.

## Security & Configuration Tips
- Never include secrets or credentials in examples; show env vars instead (e.g., `NEXT_PUBLIC_*` only for client‑safe values).
- Call out RLS requirements for any data access and note CI gates (lint + e2e) when proposing workflows.

## Agent‑Specific Instructions
- Scope: This guide applies to the entire repo.
- Make focused edits; avoid renames or restructures unless necessary.
- Prefer `apply_patch` with minimal diffs; keep changes consistent with existing naming/order.