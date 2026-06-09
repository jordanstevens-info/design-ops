---
name: eval
description: >
  Run design evals, design-system evals, design acceptance scenarios, smoke
  evals, quick evals, full evals, baseline-vs-candidate comparisons,
  fresh-context reviewer checks, or system-performance evals for design-relevant
  artifacts. Use for generated UI, prototypes, branches/MRs, Figma/static
  designs, screenshots, Storybook states, deployed screens, specs, plugin
  outputs, design-system changes, or any inspectable artifact with enough
  evidence. Do not use for broad critique without an eval frame, production
  implementation, MR packaging, backlog ticket drafting, or processing C4 data.
---

# Eval

Run an explicit design quality gate. Treat the design system as an executable
set of evals and acceptance contracts, not only a component kit.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/eval-loop.md`
- `../../references/rubrics.md`
- `../../references/resonant-frequency.md` when the artifact should be evaluated
  against a project thread, primary metric, guardrail metrics, or decision rule
- `../../references/design-system-acceptance.md` when design-system fit,
  design acceptance, or acceptance scenarios are requested
- `../../references/smoke-evals.md` for smoke evals
- `../../references/system-performance.md` when evaluating this plugin,
  recipes, templates, variants, or repeated workflow quality
- `../../references/optional-delegation.md` when a fresh-context reviewer would
  reduce bias
- `../../references/capability-discovery.md` when the eval depends on Figma,
  browser, Storybook, Jira, Git, analytics, or local CLI availability

Use templates:

- `../../templates/eval/smoke-eval-report.md` for smoke evals
- `../../templates/eval/eval-report.md` for quick and full evals
- `../../templates/acceptance/design-acceptance-report.md` for design-system
  acceptance and acceptance scenarios
- `../../templates/eval/smoke-reviewer-prompt.md` when preparing a
  fresh-context reviewer
- `../../templates/eval/system-performance-report.md` for workflow/system evals
- `../../templates/eval/skill-scenario-set.md` to build or reuse a durable
  scenario set for system-performance evals
- `../../templates/output/output-contract.md` for non-trivial outputs
- `../../templates/destination/destination-policy.md` before persisting reports
- `../../templates/feedback/feedback-report.md` when findings create rerun
  constraints, required changes, design debt, exceptions, or graduation signals

Classify the eval before scoring:

- Artifact under eval and available evidence
- Eval mode: smoke, quick, full, design-system acceptance, or system-performance
- Decision needed: move forward, rerun, gather evidence, accept with changes,
  request exception, or stop
- Design-system profile, acceptance profile, rubric, or extension lens used
- Resonant frequency and decision rule, if available
- Whether fresh-context review is useful or unavailable
- Data handling boundary and prohibited-source risk

If source material is known or suspected C4, stop as `Prohibited`; do not
summarize, quote, redact, transform, infer from, or generate from the source.

Mode rules:

- Smoke eval: ask one diagnostic question, return `Pass`, `Needs work`, or
  `Fail`, and do not claim acceptance.
- Quick eval: run a lightweight rubric pass, label it diagnostic, and report
  confidence plus missing evidence.
- Full eval: freeze input and output refs, track contamination notes, use a
  named rubric/profile, and produce rerun constraints.
- Design-system acceptance: generate or evaluate acceptance scenarios against
  tokens, components, patterns, states, accessibility, content, and allowed
  exceptions.
- System-performance eval: evaluate whether the plugin, recipe, template, or
  workflow produced the right artifact quality and what should graduate. Score
  the run, not just the artifact: report deterministic checks (trigger, steps,
  required outputs, data handling, permissions) separately from rubric judgment
  (quality, fit, usefulness). For recurring or comparable workflows, use a
  durable scenario set with negative controls, and for a change to a skill,
  recipe, template, or variant, score baseline against candidate over the same
  scenarios and report the delta.

If the resonant frequency is missing on an artifact that needs directional
quality judgment, name that as missing evidence or route to scope backfill
instead of inventing a metric.

For design-system evals, use acceptance scenarios as the primary review
artifact. Cover the primary path, interaction states, responsive behavior,
loading/empty/error states where relevant, accessibility/focus, content edge
cases, and exception/debt checks.

Persona diagnostics are a future extension lens. If asked to run a persona eval
before a persona framework is available, state the missing persona inputs and
propose a rerun path. Do not invent personas. Persona diagnostics are not user
validation; they should feed test plans, acceptance questions, or follow-up
changes.

Output the report inline unless the user asks to persist it. Include findings
first when there are blockers, then missing evidence, required changes or
scenarios, confidence or verdict, contamination notes, stop condition, feedback
report need, and rerun instruction.
