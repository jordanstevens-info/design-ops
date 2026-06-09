---
name: init-os
description: >
  Use when the user wants to initialize, install, set up, overlay, migrate,
  upgrade, version-stamp, or audit a local Work OS folder. This is the public
  Work OS plugin entry point; it installs and upgrades local Work OS skills
  rather than owning day-to-day Work OS use. Named `init-os` to avoid colliding
  with the host's native `/init` command.
---

# Work OS Init-OS

Initialize or upgrade a local Work OS. This marketplace skill is an installer,
migrator, and upgrade planner. Daily Work OS work should happen through the
local skills it installs: `work-os-prime`, `work-os-report`,
`work-os-feedback`, `work-os-reflect`, and `work-os-audit`.

Path resolution: resolve `references/` and `templates/` from the directory
containing this `SKILL.md`. If a host installs or exposes this skill from a
rewritten location, locate the nearest parent that contains this skill's sibling
`references/` and `templates/` directories, then resolve bundled Work OS assets
from that skill root.

## Read When Needed

- `references/branch-policy.md` when Git state or branch choice affects writes.
- `references/init-workflow.md` for setup modes and approval gates.
- `references/upgrade-model.md` for manifest comparison and local skill
  upgrades.

## Bundled Templates

- `templates/work-os/manifest.template.json` - target manifest shape.
- `templates/local-skills/*.md` - local skill templates. Copy each file to
  `.agents/skills/<name>/SKILL.md` and `.claude/skills/<name>/SKILL.md`.
  Copy any sibling resource folder, such as `work-os-report/references/`,
  alongside the installed skill.
- `templates/scaffold/` - the non-skill scaffold layer, laid out as a 1:1
  mirror of the install target. It carries the root `AGENTS.md` router and
  `CLAUDE.md` adapter, the `personal/` router pair plus `personal/feedback/`
  index seed, `drop-zone/` and `sandbox/` README seeds, `context/templates/*`
  (shared artifact shapes + README), `context/knowledge/work-os/*` doctrine plus
  `context/knowledge/README.md`, and a `context/feedback/` index seed. Installed
  in full on `fresh`; install-if-missing, never-overwrite, on `overlay`,
  `upgrade`, and `refactor`. These assets are not version-tracked — the user
  owns them after install.

## Template Resolution

Before saying bundled templates are unavailable, locate them explicitly. Check
these locations in order:

1. The directory containing this `SKILL.md`:

   ```bash
   find templates/local-skills \
     -maxdepth 2 -type f -name '*.md' -print
   ```

2. The nearest parent that contains `skills/init-os/templates/local-skills` when
   the host exposes a plugin root instead of a skill directory:

   ```bash
   find . -path '*/skills/init-os/templates/local-skills/*.md' -print
   ```

3. The installed Codex plugin cache:

   ```bash
   find "${CODEX_HOME:-$HOME/.codex}/plugins/cache/design-ops/work-os" \
     -path '*/skills/init-os/templates/local-skills/*.md' -print
   ```

4. The installed Claude Code plugin cache:

   ```bash
   find "${CLAUDE_CONFIG_DIR:-$HOME/.claude}/plugins/cache/design-ops/work-os" \
     -path '*/skills/init-os/templates/local-skills/*.md' -print
   ```

5. The Claude Code marketplace checkout:

   ```bash
   find "${CLAUDE_CONFIG_DIR:-$HOME/.claude}/plugins/marketplaces/design-ops/plugins/work-os/skills/init-os/templates/local-skills" \
     -maxdepth 2 -type f -name '*.md' -print
   ```

6. The source checkout when running from this repository:

   ```bash
   find plugins/work-os/skills/init-os/templates/local-skills \
     -maxdepth 2 -type f -name '*.md' -print
   ```

Use the directory that contains `work-os-prime.md`, `work-os-report.md`,
`work-os-feedback.md`, `work-os-reflect.md`, and `work-os-audit.md` as the local
skill template root. Resolve the manifest template from the same skill root at
`templates/work-os/manifest.template.json` when present.

Once the local-skills root is found, resolve the scaffold layer at the same
skill-root level under `templates/scaffold/`. It is a soft dependency: if
`templates/scaffold/` is absent, note it in the pre-write summary and continue —
do not abort. The skill still installs local skills and the manifest without it.

If none of these probes finds templates, stop as `Plan only` and report the exact
commands and paths checked.

## Core Rules

- Proposal-first. Inspect and propose before writing unless the user explicitly
  asks for a narrow manifest-only write.
- Prefer yes/no or approve/decline choices over open-ended setup questions.
- Never auto-refactor existing folders.
- Never overwrite local skills or routers without showing the change.
- Never store secrets, tokens, cookies, private config, `.env`, or credentials.
- If the target is Git-tracked, propose a new branch for setup, migration, or
  upgrade work unless local manifest policy says updates may happen in place.
- If the target is not Git-tracked, propose Git initialization plus a new branch
  before migration or upgrade work. Let the user decline.
- Keep `AGENTS.md` and `memory.md` under 4,500 characters; route bulky doctrine
  to `context/knowledge/`.
- Install local skills into both `.agents/skills/` and `.claude/skills/`.

## First Pass

Gather all first-contact signals in one pass before proposing anything. Git is
one signal among several, not the lead. Present a consolidated summary, then
offer choices.

1. Identify the target folder. Default to the current working directory.
2. Collect signals:
   - **Manifest**: check `context/knowledge/work-os/manifest.json` — present,
     missing, or corrupt. If present, read `workOsVersion` and skill versions.
   - **Structure**: scan one level deep — empty, has useful folders, has an
     existing Work OS shape, or has a manifest but no local skills.
   - **Template availability**: confirm bundled templates are reachable (run
     the **Template Resolution** probe). Note if unavailable.
   - **Git**: run `git rev-parse --is-inside-work-tree`. If tracked, run
     `git status --short --branch` for the current branch and dirty/clean
     state. If untracked, note that git-init will be offered.
   - **Skill-root sync**: if `.agents/skills/` or `.claude/skills/` exist, note
     whether they are present and roughly in sync. The full diff runs later in
     **Upgrade Audit Contract**, not here.
   - **Sensitive material or unusual size**: flag obvious credential files or a
     very large tree. Do not enumerate contents.
3. Classify the run from the signals above:
   - `fresh` - empty or intentionally clean folder.
   - `overlay` - existing useful structure should remain in place.
   - `refactor` - user wants a migration map for messy structure.
   - `upgrade` - existing Work OS manifest or local skills are present.
   - `audit` - read-only health check before setup or upgrade.
4. Present the consolidated summary and proposed action as explicit choices
   (see **Approval Prompts**).

## Approval Prompts

After the **First Pass** scan, present a compact summary, then offer choices.
The summary has up to four rows — mode, manifest, git, and skill drift. Omit any
row that adds no signal. Git is one row, not the headline.

Git-tracked target:

```text
Found:
  Mode:     upgrade (manifest v0.2.0, 3 skills installed)
  Manifest: context/knowledge/work-os/manifest.json — present
  Git:      branch `main`, tree clean — recommend new branch `work-os/<slug>`
  Skills:   work-os-report template-newer, work-os-audit missing

Proposed: create branch `work-os/<slug>`, upgrade work-os-report, install
work-os-audit, update manifest.

Options:
1. Approve branch-backed update
2. Plan only (no writes)
3. Continue on current branch
4. Cancel
```

Untracked target — git-init is one line in the proposal, not the whole question:

```text
Found:
  Mode:     fresh
  Manifest: none
  Git:      not tracked — git init + branch `work-os/setup` recommended

Proposed: git init, create branch `work-os/setup`, scaffold full Work OS
structure, install all skills.

Options:
1. Approve (includes git init and branch)
2. Plan only (no writes)
3. Proceed without Git
4. Cancel
```

Do not ask broad open-ended questions when an approval choice is enough.

## Upgrade Audit Contract

The bundled `templates/work-os/manifest.template.json` `skills` map is the
authoritative version registry. Skill `SKILL.md` files do not carry a version;
the bundled manifest declares the version each template ships at, and the local
`context/knowledge/work-os/manifest.json` records the version each installed
skill was last set to. Compare those two maps for version drift, and use a
content diff against the bundled template as the proof of what actually changed.

Before proposing any template-based local skill change:

1. Inventory bundled `templates/local-skills/*.md` and the bundled manifest
   `skills` versions.
2. Inventory installed `.agents/skills/<skill>/SKILL.md`,
   `.claude/skills/<skill>/SKILL.md`, and the local manifest `skills` versions.
3. Classify each skill:
   - `missing` - absent from one or both local skill roots.
   - `same` - installed files match the bundled template.
   - `local-edited` - installed files differ from the template or from each
     other.
   - `template-newer` - the bundled manifest version for the skill is greater
     than the local manifest version. Confirm with a content diff before
     proposing a replacement; if versions differ but content matches, treat it
     as a manifest-version bump only.

   Compare version strings component-wise as integers (semver
   major.minor.patch), not as strings; `0.10.0` is greater than `0.9.0`.
4. For `missing`, propose install.
5. For `same`, propose no file change.
6. For `local-edited` or `template-newer`, show a focused diff and propose
   `keep local`, `replace from template`, or `merge manually`.
7. Ask for approval before installing, replacing, or merging any local skill.
   Do not treat `upgrade` as blanket permission to rewrite existing skills.
8. Treat `work-os-audit` like any other missing skill: propose install and wait
   for explicit approval.

## Install Or Upgrade

When approved:

1. Create missing Work OS structure only as needed, scoped by run mode:
   - For `fresh`: follow the full directory and file list in
     `references/init-workflow.md` "Fresh Setup" — that section is authoritative
     for the fresh shape and includes the root `AGENTS.md` router and `CLAUDE.md`
     adapter.
   - For `overlay`, `upgrade`, or `refactor`: create only
     `context/knowledge/work-os/`, `context/log/`, `.agents/skills/`, and
     `.claude/skills/` when missing. Do not force-create the full fresh shape
     over existing structure.
2. Write or merge `context/knowledge/work-os/manifest.json`. Replace the
   `installedAt` and `updatedAt` sentinels when writing:
   - First install (no prior manifest): set both `installedAt` and `updatedAt`
     to the current run date in `YYYY-MM-DD` format.
   - Every later write: set `updatedAt` to the current run date; leave
     `installedAt` unchanged.
   - Read the date from the model's context environment; a shell `date` call is
     only a fallback if the context date is unavailable.
3. Resolve the bundled template root using **Template Resolution**.
4. Run **Upgrade Audit Contract** for local skills.
5. Install the scaffold layer from `templates/scaffold/` (seed-once,
   install-if-missing, path-preserving copy to the target root):
   - `fresh`: install every file under `templates/scaffold/`, preserving its
     relative path; list each as a "new file" in the pre-write summary.
   - `overlay`, `upgrade`, or `refactor`: install only files missing at the
     target; never overwrite existing user content; report each present file as
     "already present — skipped".
   - Do not version-track or diff these assets — the user owns them after
     install.
   - If `templates/scaffold/` is unavailable, note the paths checked in the
     summary and continue.
6. Apply only the approved local skill additions, replacements, or merges:
   - For an approved install, copy `local-skills/<skill>.md` into
     `.agents/skills/<skill>/SKILL.md` and copy any sibling resource folder.
   - For an approved replacement or merge, modify only that named skill.
   - Mirror approved skill changes into `.claude/skills/<skill>/` so the two
     local skill roots stay in sync.
7. Preserve every existing local skill that was not explicitly approved for
   install, replacement, or merge.
8. Update the local manifest `skills` versions to the bundled versions for every
   skill that was installed or replaced. Leave versions untouched for skills
   kept as local edits.
9. Create a log receipt for applied setup, migration, or upgrade work.
10. Run validation:
    - `python3 -m json.tool context/knowledge/work-os/manifest.json`
    - `diff -qr .agents/skills .claude/skills`
    - `git diff --check`

## Local Skill Boundaries

- `work-os-prime` - read-only orientation.
- `work-os-report` - sourced reports and communication drafts.
- `work-os-feedback` - feedback signal intake and routing.
- `work-os-reflect` - session learning, graduation, and approved maintenance.
- `work-os-audit` - read-only structural and rule compliance inspection.

`work-os-feedback` and `work-os-reflect` may use audit findings as evidence.
`work-os-audit` never writes; `work-os-reflect` or `work-os:init-os` owns approved
changes after an audit.

## Stop Conditions

Stop and ask for approval when:

- Git state is dirty and the requested change could mix with unrelated work.
- The target has no Git tracking and the user has not approved non-Git writes.
- A local skill differs from the bundled template.
- A scaffold asset (root or personal router, doctrine, template, or surface
  seed) would overwrite an existing user file.
- A migration would move, rename, delete, or archive user files.
- Sensitive material is detected.
