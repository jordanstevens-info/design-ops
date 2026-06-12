---
name: workflow
description: >
  Use when the user has an idea, artifact, design question, or unclear starting
  point and needs help choosing the next design workflow. Use for orientation,
  triage, idea capture, workflow routing, artifact-loop recipe selection, or
  deciding between scope, prototype, eval, review, engineer, ticket, MR, demo,
  preso, and update work. Do not use when the user explicitly asks for one
  specific skill unless routing or data handling is unclear. Do not process C4
  data.
---

# Workflow

Route open-ended design work into the right next move. This is the generic
entry point for the `design` plugin; it is not a host-specific agent.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/eval-loop.md` when the next move is a quick eval, full
  eval, acceptance review, validation, or smoke eval
- `../../references/ideas.md`
- `../../references/research-validation.md` when evidence, learning,
  validation, usability testing, interviews, analytics, or research planning
  affects the next move
- `../../references/resonant-frequency.md` when the work needs a clearer
  decision thread, success metric, guardrail, story spine, or scope backfill
- `../../references/smoke-evals.md` when a fast diagnostic checkpoint would
  reduce routing, prototype, or design-change risk
- `../../references/system-performance.md` when the user is improving the
  plugin, a recipe, a template, or the workflow itself
- `../../references/team-variants.md` when generic vs team-specific behavior is
  part of the decision
- `../../references/capability-discovery.md` when the route depends on Figma,
  FigJam, Storybook, browser, Jira, Git, analytics, research, or local CLI
  availability
- `../../references/demo-work.md` when the next move is an async walkthrough or
  recorded stakeholder demo
- `../../references/context-bootstrap.md` only when repo-backed context or
  `.design/` capture is needed
- `../../references/optional-delegation.md` only when a fresh-context pass would
  reduce bias

Use templates:

- `../../templates/input/input-packet.md` when normalizing messy source input
- `../../templates/run/run-manifest.md` for non-trivial workflow routing
- `../../templates/artifact/artifact-manifest.md` when tracking outputs
- `../../templates/output/output-contract.md` for non-trivial outputs
- `../../templates/destination/destination-policy.md` before persisting or
  publishing outputs
- `../../templates/ideas/idea-entry.md` when saving or proposing idea capture
- `../../templates/research/research-packet.md` when the next move is learning
  what evidence is needed or how to get it
- `../../templates/validation/validation-plan.md` when an artifact needs
  evidence before advancing
- `../../templates/validation/validation-findings.md` when evidence has been
  gathered and needs to inform a decision
- `../../templates/eval/eval-report.md` when the next move is quick or full
  eval rather than smoke eval
- `../../templates/eval/smoke-eval-report.md` when the next move is a quick
  diagnostic quality gate
- `../../templates/eval/smoke-reviewer-prompt.md` when a fresh-context reviewer
  is available and useful
- `../../templates/eval/system-performance-report.md` when evaluating the
  workflow system itself
- `../../templates/demo/demo-outline.md` when the next move is recording a demo
- `../../templates/demo/distribution-blurb.md` when the demo needs Slack or
  email sharing text
- `../../templates/demo/feedback-questions.md` when async stakeholder feedback
  needs a clear ask
- `../../templates/feedback/feedback-report.md` when routing creates rerun
  constraints or system feedback
- `../../templates/prohibited/prohibited-run-report.md` for prohibited stops

Start by classifying:

- What artifact or idea exists now?
- Who authored or last materially changed it?
- What decision is needed?
- What risk is highest?
- What evidence is missing?
- Is the resonant frequency known, unknown, or contested?
- What data class applies?
- Which stop condition would end the run?

If the source is known or suspected C4, stop as `Prohibited`. Do not summarize,
quote, redact, transform, infer from, or generate from the source.

Routing:

- If the user only wants to park an idea, save or propose an idea entry.
- If the idea needs shape, route to `scope`.
- If the idea needs options, route to `prototype` after light scope framing.
- If evidence is missing, route to research or validation planning.
- If evidence has already been gathered, route to validation findings.
- If the user explicitly asks for an eval, design-system eval, acceptance
  scenarios, smoke eval, quick eval, full eval, baseline-vs-candidate
  comparison, fresh-context reviewer check, or system-performance eval, route to
  `eval`.
- If the route, prototype, or design change needs a quick bias-reduced check,
  route to `eval` for a smoke eval before deeper work.
- If the artifact needs an eval, choose smoke, quick, full, acceptance, or
  validation explicitly. Route standalone evals and acceptance scenarios to
  `eval`; do not imply that a smoke eval replaces full eval, design acceptance,
  or user validation.
- If an artifact exists but lacks problem framing, route to `scope backfill`.
- If meaningful design work lacks a resonant frequency, or the frequency is
  contested, route to `scope` or `scope backfill` before implementation,
  acceptance, Jira packaging, demos, or presos.
- If an MR, branch, prototype, Figma artifact, ticket, or shipped UI needs
  acceptance, route to `review`.
- If production code changes are needed, route to `engineer`.
- If delivery packaging is needed, route to `create-backlog`, `create-mr`,
  `create-demo`, `create-preso`, or `slack-update`.
- If the artifact needs async stakeholder walkthrough and feedback, route to
  `create-demo`.
- If the user is improving this plugin, a recipe, a template, or repeated run
  quality, route to `eval` for system-performance eval.

Output:

Use `../../templates/output/output-contract.md` for non-trivial routing output.
Always include the recommended recipe or `custom`, next skill to use, why that
path fits, required inputs or evidence, data handling decision, stop condition,
actor/authority fields, feedback/rerun path, next action, and proposed
destination for any idea, report, or artifact.

Hand off into the next skill only when the user asks you to continue or the next
step is explicitly requested.
