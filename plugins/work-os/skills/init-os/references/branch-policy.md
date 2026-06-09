# Branch Policy

Work OS setup, migration, and upgrade work should be easy to review and undo.

## Git-Tracked Targets

If the target folder is inside a Git worktree:

1. Read `git status --short --branch`.
2. Check `context/knowledge/work-os/manifest.json` for branch policy.
3. Prefer a new branch for setup, upgrade, or refactor work.
4. Present approval choices before switching or creating a branch.

Default branch pattern:

```text
work-os/<short-purpose>
```

If the tree is dirty, preserve it. Do not reset, checkout, clean, or stash
unless the user explicitly requests that action.

## Non-Git Targets

If the target folder is not Git-tracked, propose Git initialization before
writing setup, upgrade, or migration changes.

Recommended approval shape:

```text
Recommended: initialize Git and create `work-os/<short-purpose>` before
applying approved changes.

Options:
1. Approve Git init plus branch-backed update
2. Plan only
3. Continue without Git
4. Cancel
```

If the user declines Git, keep the write set smaller and list every file that
will be created or changed before applying.
