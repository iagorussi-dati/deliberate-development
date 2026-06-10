---
name: git
description: Git workflow conventions. Agents must read and follow the project's GIT-CONVENTIONS.md before any git operation (commit, branch, PR).
---

<what-to-do>

Before any git operation (creating branches, committing, opening PRs), read the `GIT-CONVENTIONS.md` at the project root and follow it exactly.

If no `GIT-CONVENTIONS.md` exists, use these defaults:

### Branches

- Branch from the default branch (usually `main` or `dev`)
- `feat/XX-slug` for features, `fix/XX-slug` for bugs (XX = issue number)

### Commits

- Conventional commits in English: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `test:`

### PRs

- 1 issue = 1 PR
- Always include `Closes #XX` in the PR description
- Open the PR, wait for CI, ask human for confirmation, then merge after approval

### Labels

Only these labels exist:

- `prd` — issue is a PRD (feature spec)
- `prd:needs-grill` — PRD needs refinement before it can be broken into issues
- `ready-for-agent` — issue is ready for an AFK agent to implement
- `bug` — bug reported by QA (always paired with `ready-for-agent`)

### Issue lifecycle

1. PRD created → `prd` + `prd:needs-grill`
2. After grill → remove `prd:needs-grill`, keep `prd`
3. `to-issues` breaks PRD into child issues → each child gets `ready-for-agent` and references the parent PRD
4. QA bugs → `bug` + `ready-for-agent`, linked to the originating PRD

### Closing issues (mandatory)

- **Always close issues you worked on** — via `Closes #XX` in the PR
- Before finishing, check if all child issues of the parent PRD are closed
- If all children are closed, close the parent PRD too

</what-to-do>

<rules>

1. **Always read `GIT-CONVENTIONS.md`** at the project root before your first git operation in a session. If it exists, follow it exactly — it overrides the defaults above.
2. **Branch naming**: follow the convention defined there (e.g., `feat/XX-slug`, `fix/XX-slug`).
3. **Commits**: follow the commit convention defined there (language, format, scope).
4. **PRs**: follow PR conventions. Always include `Closes #XX`. Ask human for merge confirmation.
5. **Never push directly** to protected branches (usually `main` and `dev`) — always via PR.
6. **1 issue = 1 PR** unless the conventions say otherwise.
7. **Close your issues** — this is mandatory. Never leave issues open after completing the work.

</rules>
