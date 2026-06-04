---
name: git
description: Git workflow conventions. Agents must read and follow the project's GIT-CONVENTIONS.md before any git operation (commit, branch, PR).
---

<what-to-do>

Before any git operation (creating branches, committing, opening PRs), read the `GIT-CONVENTIONS.md` at the project root and follow it exactly.

If no `GIT-CONVENTIONS.md` exists, use these sensible defaults:
- Branch from the default branch
- Use conventional commits in English (`feat:`, `fix:`, `docs:`, `chore:`)
- Open PRs with a clear description
- Reference issues with `Closes #XX` when applicable

</what-to-do>

<rules>

1. **Always read `GIT-CONVENTIONS.md`** at the project root before your first git operation in a session.
2. **Branch naming**: follow the convention defined there (e.g., `feat/XX-slug`, `fix/XX-slug`).
3. **Commits**: follow the commit convention defined there (language, format, scope).
4. **PRs**: follow PR conventions (title language, description language, `Closes #XX`).
5. **Never push directly** to protected branches (usually `main` and `dev`) — always via PR.
6. **1 issue = 1 PR** unless the conventions say otherwise.
7. **Assign yourself** to the issue before starting work, if possible.

</rules>
