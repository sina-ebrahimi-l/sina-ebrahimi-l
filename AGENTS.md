# Repository-wide infrastructure policy (Sina Ebrahimi)

Read this policy before proposing code, automation, CI, deployment, or architecture changes. This is a standing owner preference, not a claim that every legacy integration has already been removed.

- **Primary deployment:** self-managed VPS / Coolify (or another explicitly approved self-hosted server deployment). Validate with server-side checks, health endpoints, logs, and smoke tests.
- **Do not default to Vercel.** Vercel may be used only for explicitly requested previews/experiments; do not move production to Vercel without owner approval.
- **Do not default to GitHub Actions.** GitHub is used for version control, PRs, review and task tracking. Existing GitHub Actions `startup_failure` is not by itself a merge blocker; run appropriate independent tests and verify server deployment. Do not add new Actions workflows without approval.
- **Do not default to Google Apps Script.** Prefer the existing VPS/self-hosted services and APIs. Existing legacy integrations should not be removed or migrated without explicit scope and approval.
- **Safety:** no production data migrations, destructive operations, secrets/OAuth/DNS changes, extra costs, or public releases without explicit owner approval. Never expose credentials or customer data.
- **Review and merge:** require relevant passing tests, no unresolved conflicts, assessed production impact, and post-deployment smoke tests when applicable.
- **Coordination:** consult `sina-ebrahimi-l/project-hub` for cross-project priorities and constraints. Preserve project-specific instructions; if they conflict, ask the owner rather than silently overriding.
