# Bootstrap

Run once per repo when `.design/` does not yet exist. Triggered automatically on
first use or via "Preflight" / "Prime".

## Branch

1. Create a `design/<feature-name>` branch from the primary branch
2. Do all work on this branch
3. When optional delegation is available and useful for implementation support,
   keep delegated work isolated from the primary branch/worktree where the host
   supports that mode

## Detect

Run silently before asking questions. Scan for:

- Language/runtime (manifest files: `package.json`, `Cargo.toml`, `pyproject.toml`, `go.mod`, etc.)
- Package manager (lockfiles: `pnpm-lock.yaml`, `yarn.lock`, `package-lock.json`, etc.)
- Monorepo signals (`pnpm-workspace.yaml`, `turbo.json`, `nx.json`, workspaces config)
- Git state (primary branch, recent commits, remote URL)
- Existing infrastructure: `AGENTS.md`, `CLAUDE.md`, `knowledge/`, `docs/`,
  `doc/`, `CONTRIBUTING.md`, `ARCHITECTURE.md`, `README.md`, `.github/`
- Design system files: token definitions, component libraries, theme configs
- Source routers: Jira, Confluence, Figma/FigJam, Storybook, analytics, issue
  trackers, repo docs, or team working agreements referenced by local files

## Create `.design/`

Resolve knowledge sources in priority order:

1. **Repo's own `AGENTS.md` or `CLAUDE.md`** — if either points to
   knowledge/context files, reference those
2. **Repo's existing docs** — scan `knowledge/`, `docs/`, `doc/`,
   `CONTRIBUTING.md`, `ARCHITECTURE.md`, `README.md`, or any path referenced in
   `AGENTS.md` or `CLAUDE.md`
3. **Buttress with `.design/knowledge/`** — for anything the repo doesn't provide,
   create from bundled `templates/design-context/` files
4. **Standalone fallback** — if the repo has nothing, create the full knowledge set
   in `.design/knowledge/` using all bundled templates

Then:

- Create `.design/README.md` from `templates/design-context/README.md` — document which sources
  were found (and where) vs. created
- Create `.design/knowledge/design-system.md` from `templates/design-context/design-system.md` —
  populate with tokens, components, and conventions discovered during detection
- Create `.design/knowledge/context-map.md` from `templates/design-context/context-map.md`
  when source routers, tools, or external systems are discovered
- Create `.design/knowledge/sources.md`, `tooling.md`, or
  `working-agreements.md` only when there is real content to record
- Create `.design/ideas.md` from `templates/ideas/idea-entry.md` only when the
  user asks to capture a real repo-backed idea or an active workflow produces an
  idea worth parking

Do NOT create empty directories. Create `changelog/`, `artifacts/`, `presos/`,
and `tmp/` only when there is content to put in them.

When `tmp/` is first created, add `.design/tmp/` to the repo's `.gitignore`.

## Interview (only if no existing knowledge)

If the repo has no `AGENTS.md`, no `CLAUDE.md`, no `knowledge/` directory, and
no meaningful docs, ask in a single prompt:

1. What is this project? (one-liner)
2. What problem does it solve and who is it for?
3. Current state? (POC / MVP / production / maintenance / greenfield)
4. What's the next milestone?
5. What's explicitly out of scope?

If repo already has knowledge files, skip the interview — read what exists.
