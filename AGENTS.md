# AGENTS.md — 14-Agent-Squads (Repo Root)

This file guides coding agents (e.g., Codex CLI) in this repo. Keep behavior deterministic, tool-first, and low-risk.

---

## Project scope & guardrails

- **Monorepo intent:** Treat each of the **14 agent modules** as separate packages. Stay within the **current module** unless explicitly instructed otherwise.
- **Change policy:** Before broad edits, print a one-line plan (see “Operating ritual”). Propose cross-module changes before editing.
- **Safety:** Prefer non-destructive changes. Create small, reviewable diffs. Don’t move or delete files unless the plan states why.

---

## MCP policy (tool-first, low drift)

We use three MCP servers. **Decision order and triggers:**

1) **Context7 — docs freshness (highest priority)**
   - **When:** Any task that depends on library/framework/product docs (APIs, config, CLI flags, migrations, breaking changes).
   - **Do:** Call Context7 first to pull **version-specific** docs/snippets for the libraries in play. If writing code against a lib, refresh docs before generating code.
   - **Failover:** If Context7 fails twice, say so and proceed with best-practice patterns, noting assumptions.

2) **Zod (v4) — validation expertise**
   - **When:** Anything touching validation schemas, `safeParse/parse`, `refine/superRefine`, `z.infer`, discriminated unions, `coerce/transform`, v3→v4 nuances.
   - **Do:** Use **`search-zod-v4-docs`** first to locate relevant sections/issues/release notes. If results are unclear or conflicting, call **`ask-question-about-zod-v4`** and summarize guidance before coding.
   - **Defaults:** Prefer `safeParse` in app code; surface `.error` nicely; choose narrow, explicit types; use discriminated unions for variants.

3) **Supabase MCP — data & platform tasks (read-first)**
   - **Default:** **Read-only** and **project-scoped**. Do **not** run mutating tools without proposing a plan and getting explicit approval.
   - **Typical tools:** Knowledge (`search_docs`), Database (`list_tables`, `execute_sql` — reads by default), Debugging (`get_logs`, `get_advisors`), Dev helpers (`generate_typescript_types`, `get_project_url`, `get_anon_key`).
   - **Write operations:** Only with approval and a step-by-step plan (goal → SQL/operation → risk/rollback → approval). Assume writes are **not permitted** unless stated.

---

## Operating ritual (print this before acting)

`Plan: <Context7|Zod|Supabase> → cite doc source → propose diff (scope, files) → implement minimal change → run quick checks → summarize outcome`

- **Citations:** After using a docs MCP (Context7/Zod/Supabase docs), name the doc and section you relied on and quote the key line when practical.
- **Scope:** Keep changes to the **current module** unless the plan explicitly expands scope.
- **Quick checks:** If the module has scripts/tests/linters, run the smallest practical check and include a brief result.

---

## Hard DO / DON’T

**DO**
- Use **Context7** before writing code that depends on third‑party APIs or framework behavior.
- With **Zod**: prefer `safeParse`, precise constraints (e.g., `z.string().min(...)`, `z.number().int()`), discriminated unions for variants; explain v3→v4 differences when relevant.
- With **Supabase MCP**: default to reads; for writes propose a plan with rollback.
- Keep diffs minimal; include a short “why” in the PR and reference the doc snippet used.

**DON’T**
- Don’t invent APIs that aren’t in docs; if unsure, re‑query Context7 or ask the Zod/Supabase tools.
- Don’t edit unrelated modules. Keep diffs focused and scoped.
- Don’t run destructive DB operations without explicit approval and a rollback step.

---

## Failure handling

- If any MCP endpoint is unreachable **twice**, state that it’s unreachable and continue with best practice, noting assumptions and risk.
- If retrieved docs conflict, prefer the **newest stable release notes** or official migration guides; otherwise summarize the conflict and ask before proceeding.

---

## Quick references (tool names you’ll see)

- **Context7**: remote/local MCP that injects **version‑specific** docs/snippets into context.
- **Zod (v4) MCP tools:**
  - `search-zod-v4-docs` — search docs, GitHub issues, release notes, help center.
  - `ask-question-about-zod-v4` — direct expert Q&A.
- **Supabase MCP tool examples:**
  - Knowledge: `search_docs`
  - Database: `list_tables`, `execute_sql` (read-first)
  - Debugging: `get_logs`, `get_advisors`
  - Dev: `generate_typescript_types`, `get_project_url`, `get_anon_key`

---

## Approvals & secrets

- Treat all tokens/keys as sensitive; never print secrets in chat or logs.
- Any **write** to Supabase or cross‑module refactor requires an explicit “OK to proceed” after the plan.
- Prefer non‑interactive changes; if a task would affect CI/CD, call that out before editing.

---

## House style & repo execution policy

- **Modules & naming:** Use two‑digit prefixes; maintain paired `builder`/`qa` docs per topic to keep scope clear.
- **Quick checks:** Run markdown lint + link check; keep lines to a readable length (~100–120 chars).
- **Style:** Defer to `globals/style_guide.md` (Australian English; consistent tokens; TypeScript strict).
- **Testing:** Satisfy `globals/acceptance_criteria.md` and cross‑check `globals/guardrails.md` when relevant.
- **Commits/PRs:** Use Conventional Commits (`feat|fix|docs|chore(scope): summary`). PRs must state purpose, scope, related links, and proof (screenshots/logs).
- **Security hygiene:** No secrets in examples; call out RLS or access‑control implications; respect CI gates.
- **Edit discipline:** Prefer focused diffs; preserve naming/order unless there’s a documented reason; prefer `apply_patch`‑style atomic edits when available.

---

## Example prompts (for agents)

- “Plan: Context7 → fetch latest Zod v4 docs on discriminated unions → propose schema change in `modules/validation` → implement → run markdown/link checks.”
- “Plan: Supabase MCP (read-only) → list tables + generate TS types → propose usage in `modules/api` → implement small change.”
- “Plan: Zod docs search → compare `safeParse` vs `parse` error handling → patch `parse` to `safeParse` in module → add error surface.”

