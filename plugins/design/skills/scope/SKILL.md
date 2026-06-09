---
name: scope
description: >
  Create designer-owned planning artifacts for design work: design
  scope, research plan, QA plan, competitive-analysis brief, or team-facing
  design plan. Also use for scope backfill when an existing prototype, branch,
  MR, or stakeholder artifact lacks problem framing, target users, decision
  criteria, or evidence. Do not use for Jira/backlog ticket creation,
  MR packaging, prototyping, production code changes, acceptance review, or
  processing C4 data.
---

# Scope

Create a shareable design planning artifact. Use `.design/` context if present,
but do not require bootstrap unless the user asks to scope repo-backed
implementation work.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/design-scope.md`
- `../../references/resonant-frequency.md`
- `../../references/research-validation.md` when creating research or
  validation plans or findings
- `../../references/pm-seams.md`
- `../../references/context-bootstrap.md` only when repo-backed bootstrap is
  required or requested

Use templates from `../../templates/scope/`; use shared packet/report templates
from `../../templates/input/`, `../../templates/run/`,
`../../templates/research/`, `../../templates/validation/`,
`../../templates/output/output-contract.md`,
`../../templates/destination/destination-policy.md`, and
`../../templates/feedback/` when the run needs lineage or handoff.
Use `../../templates/scope/scope-backfill.md` when an artifact already exists
before the problem, target user, decision, or evidence is framed.

Output using `../../templates/output/output-contract.md` for non-trivial scope
work. Include the selected artifact type, source context used, open questions,
resonant frequency if meaningful design work is being framed, destination
decision, actor/authority fields, stop condition, feedback/rerun path, and
recommended next design action. Produce a feedback report when the scope creates
rerun constraints, validation needs, or required evidence. Stop as `Prohibited`
if the source material is known or suspected C4.
