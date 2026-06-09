---
name: create-preso
description: >
  Create a design story presentation package: narrative, one-pager, deck
  outline, demo script, feedback questions, and impact signals. Use when a
  designer needs to present or share the design story. Do not use for ticket
  creation, MR packaging, prototyping, engineering, review, or processing C4
  data.
---

# Create Preso

Create a design story package. For repo-backed work, place it under
`.design/presos/<topic>/`.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/design-story.md`
- `../../references/resonant-frequency.md` when the presentation needs a clear
  story thread, success metric, guardrail, or decision frame
- `../../references/capability-discovery.md` when Figma, FigJam, slides, or doc
  tool availability affects the package
- `../../references/context-bootstrap.md` only when repo-backed context is
  required or requested

Use templates from `../../templates/preso/`, plus
`../../templates/output/output-contract.md` for non-trivial outputs and
`../../templates/destination/destination-policy.md` before persisting or
publishing presentation artifacts.

Output the package files or inline artifacts, source context used, feedback
questions, success signals, destination decision, actor/authority fields, stop
condition, feedback/rerun path, and next action. Stop as `Prohibited` if source
material is known or suspected C4.
