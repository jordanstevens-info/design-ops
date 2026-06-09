---
name: create-demo
description: >
  Create an async demo package for a prototype, branch, plugin, Figma artifact,
  MR, or design concept: recording outline, demo path, talking points, exact
  lines when needed, links, feedback questions, and distribution blurb. Use
  when the user needs to record and share a one-way demo for asynchronous
  stakeholder feedback. Do not use for live presentations, ticket creation, MR
  packaging, engineering, review, or processing C4 data.
---

# Create Demo

Create an async demo package. For repo-backed work, place it under
`.design/demos/<topic>/`.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/demo-work.md`
- `../../references/resonant-frequency.md` when the demo needs a story thread,
  success metric, guardrail, or decision framing
- `../../references/communication-work.md` when drafting the distribution blurb
- `../../references/capability-discovery.md` when prototype, Figma, browser, or
  runtime links are needed for setup
- `../../references/context-bootstrap.md` only when repo-backed context is
  required or requested

Use templates from `../../templates/demo/`, plus
`../../templates/output/output-contract.md` for non-trivial outputs and
`../../templates/destination/destination-policy.md` before persisting or sharing
demo artifacts.

Output:

- demo intent and audience
- resonant frequency as the story thread, when available
- recording outline
- setup links and demo path
- talking points, not a word-for-word script
- exact lines only for claims, metrics, decisions, or required framing
- feedback questions
- distribution blurb
- follow-up path for received feedback
- destination decision and stop condition
- actor/authority fields, feedback/rerun path, and next action

Never publish or upload the demo. The user records, edits, and distributes it.
If source material is known or suspected C4, stop as `Prohibited`; do not
summarize, quote, redact, transform, infer from, or generate from the source.
