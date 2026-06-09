# Init Workflow

## Fresh Setup

Use when the target directory is empty or the user wants a clean Work OS.

Create only the minimum useful shape. Files marked "seeded" are installed from
`templates/scaffold/` (see SKILL.md "Install Or Upgrade" step 5):

- root router and Claude adapter when missing (seeded: `AGENTS.md`, `CLAUDE.md`)
- `context/knowledge/work-os/` (seeded: `context-protocol`,
  `operating-principles`, `graduation-patterns`, `progress-visibility`, and
  `context/knowledge/README.md`)
- `context/templates/` (seeded: `feedback`, `received-feedback`,
  `project-feedback`, `log`, `scope`, `idea`, and `README.md`)
- `context/feedback/` (seeded: empty index `README.md`)
- `context/log/`
- `drop-zone/` (seeded: `README.md`)
- `sandbox/` (seeded: `README.md`)
- `personal/` (seeded: `AGENTS.md`, `CLAUDE.md`, `feedback/README.md`)
- `.agents/skills/`
- `.claude/skills/`

Do not create `workspaces/` during fresh setup. It is an available surface,
created only when team, company, or client work earns it.

Seed setup tasks for missing goals, tooling profiles, source maps, and active
work instead of forcing full capture during first run.

## Overlay Existing Structure

Use when the target already has useful folders.

Inspect the tree, identify likely goals/tasks/projects/references, and add Work
OS routers and skills around the existing structure. Do not move existing files
without a separate approved migration map.

## Refactor Existing Structure

Use when the user asks to normalize a messy folder.

Produce a before/after migration map first. The apply step must be explicit and
should run on a branch when Git is available.

## Upgrade Existing Work OS

Use when a manifest or local Work OS skills already exist.

Compare local manifest and skill files with bundled templates. Replace only
unchanged or approved local files. Preserve local edits by default.

## Audit Mode

Use read-only audit before risky setup or upgrade. The audit checklist may be
run by this init-os skill before local `work-os-audit` exists. Once installed,
`work-os-audit` owns recurring health checks.
