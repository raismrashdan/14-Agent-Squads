# Global Guardrails
- Never expose server secrets in client bundles.
- All tables with user data must have RLS policies.
- TypeScript strict; no `any` unless justified.
- Analytics only when env var present.
- Accessibility: keyboard nav + focus-visible styles.
- CI must pass lint + e2e before merge.
