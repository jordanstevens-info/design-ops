---
name: review
description: >
  Review design artifacts for design acceptance, readiness, or critique:
  MRs, branches, prototypes, tickets, Figma/static designs, screenshots, or
  another designer's work. Use for design-quality findings and acceptance risk.
  Use eval instead when the user explicitly asks for eval modes, design-system
  evals, acceptance scenarios, baseline-vs-candidate comparisons, or
  system-performance evals. Do not use for broad code review,
  implementation-only review, scoping, prototyping, ticket drafting, MR package
  creation, or processing C4 data.
---

# Review

Classify the target first, then run the appropriate design review.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/eval-loop.md`
- `../../references/review-work.md`
- `../../references/resonant-frequency.md` when reviewing whether an artifact
  advances the project thread, metrics, guardrails, or decision rule
- `../../references/design-system-acceptance.md` for MR/PR, branch,
  implementation-intent prototype, or system-fit acceptance
- `../../references/rubrics.md`
- `../../references/smoke-evals.md` for quick diagnostic checks that do not
  need full acceptance review
- `../../references/codebase-work.md` only for branch/current-work design QA
- `../../references/mr-package.md` only for MR acceptance context
- `../../references/optional-delegation.md` when a fresh-context review pass
  would reduce bias

Use templates:

- `../../templates/output/output-contract.md` for non-trivial outputs
- `../../templates/destination/destination-policy.md` before persisting reports
- `../../templates/acceptance/design-acceptance-report.md` for design-system or
  MR-first acceptance
- `../../templates/eval/eval-report.md` for quick or full eval reports
- `../../templates/eval/smoke-eval-report.md` for quick diagnostic review
- `../../templates/eval/smoke-reviewer-prompt.md` when preparing a
  fresh-context reviewer
- `../../templates/feedback/feedback-report.md` when findings create rerun,
  required-change, decision, evidence, blocked/prohibited, rerun, or graduation
  follow-up

Target classes:

- MR or PR: design acceptance review.
- Current branch or design branch: pre-submit design QA.
- Ticket: backlog readiness and acceptance clarity.
- Prototype: design critique and exploration gaps.
- Smoke eval: quick pass/needs-work/fail checkpoint before deeper review.
- Quick or full eval: rubric-based evaluation with evidence quality, confidence,
  and rerun constraints.
- Design-system eval or acceptance scenarios: use `eval` unless the user asks
  for broader critique or MR/design acceptance.
- Figma/static design: implementation-readiness and state coverage.
- Another designer's work: critique with feedback questions and risks.

Output findings first, ordered by severity, followed by missing evidence and an
acceptance/readiness/critique summary. Use
`../../templates/output/output-contract.md` for non-trivial review output. For
MR-first acceptance, include a merge recommendation. Smoke eval remains
diagnostic and must not replace full eval, design acceptance, or user
validation. If the resonant frequency is missing and the review depends on
directional judgment, call that out as missing framing or route to scope
backfill. Produce a standalone feedback report when the result is
`Accepted with required changes` or needs a rerun, decision, evidence,
blocked/prohibited stop, or graduation. If source material is known or suspected
C4, stop as `Prohibited`; do not summarize, quote, redact, transform, infer
from, or generate from the source.
