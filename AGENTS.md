# JS Plugins

This repository is a Claude Code and Codex plugin marketplace. It has no app
runtime. The working surface is plugin manifests, skills, shared references, and
templates loaded by host CLIs on install.

## Layout

- `.claude-plugin/marketplace.json` is the Claude Code marketplace manifest.
  Each `source` path must exist under `plugins/`.
- `.agents/plugins/marketplace.json` is the Codex marketplace manifest. Entries
  use `source.source`, `source.path`, `policy`, and `category`.
- `plugins/<plugin>/.claude-plugin/plugin.json` is the Claude plugin manifest.
- `plugins/<plugin>/.codex-plugin/plugin.json` is the Codex plugin manifest with
  richer interface metadata.
- `plugins/<plugin>/skills/<skill>/SKILL.md` is the skill definition with YAML
  frontmatter. `name` and `description` drive trigger matching.
- `plugins/<plugin>/references/` is shared workflow doctrine.
- `plugins/<plugin>/templates/` is reusable artifact templates.

## Plugins

- `design`: one design workflow plugin with `workflow` plus focused skills for
  scope, prototype, engineer, eval, review, jira-update, create-mr, create-demo,
  create-preso, and slack-update. It preserves `.design` context bootstrapping, adds the
  artifact-loop contract, idea capture, and detailed doctrine in shared
  references.
- `live-canvas`: a single skill providing an infinite canvas of live iframe
  artboards for multi-viewport review and branch comparison.
- `work-os`: one public `init` skill that initializes or upgrades local
  Work OS folders, writes version manifests, and installs local prime, report, feedback, reflect,
  and audit skills.

## Working in This Repo

- Skill triggering depends on the `description:` field in frontmatter. Be
  specific about when a skill should fire.
- Design workflows use focused skills, not command shims.
- Keep shared doctrine in plugin-level `references/` and `templates/`.
- In skill files, write shared asset links relative to the directory containing
  that `SKILL.md`; if a host rewrites install paths, resolve from the nearest
  parent containing both `references/` and `templates/`.
- Do not package custom agents in plugins unless the host plugin spec adds a
  supported agent surface. Use optional delegation guidance inside skills
  instead.
- When adding or removing public plugins, update both root marketplaces.
- After editing a skill or manifest, reinstall and exercise the plugin in the
  target host CLI.
