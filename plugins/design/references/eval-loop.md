# Eval Loop

Use evals to decide whether an artifact should move forward, rerun, gather more
evidence, or stop. Evals are not all the same.

In an eval-first design-system loop, the design system acts as executable
acceptance criteria. Components, tokens, and patterns are inputs to the eval;
acceptance scenarios are what make generated or built outputs reviewable.

## Modes

- **Smoke eval:** one fast diagnostic question. Use for routing risk,
  prototype risk, or design-change risk. It returns `Pass`, `Needs work`, or
  `Fail` and does not replace acceptance review or validation.
- **Quick eval:** a lightweight rubric pass for local iteration. It can use
  current context, but must label confidence and missing evidence.
- **Full eval:** freezes input and output refs, uses a named rubric/profile,
  tracks contamination risk, and produces rerun constraints.
- **Acceptance review:** decides whether an artifact meets design,
  design-system, MR, or delivery acceptance. It can include required changes.
- **Design-system eval:** defines or checks acceptance scenarios against a
  design-system profile, acceptance profile, fixture, or known maturity state.
- **Validation:** gathers external evidence about whether the artifact works for
  the intended people, task, and decision. AI persona testing is diagnostic only.

## Report Rules

Use `templates/eval/eval-report.md` for quick and full evals. Use
`templates/eval/smoke-eval-report.md` for smoke evals. Use
`templates/acceptance/design-acceptance-report.md` for acceptance decisions.

Every report should include the artifact refs, evidence quality, missing
evidence, confidence, stop condition, and rerun instruction. Create a feedback
report whenever findings should constrain the next run.

Keep fast and thorough modes distinct. Candidate-only diagnostics, smoke evals,
and quick evals must not be reported as frozen scored matrices. Full evals
should freeze refs, name the rubric/profile, track contamination notes, and
state rerun constraints.

Persona diagnostics are a future extension lens. Do not invent personas or
present persona diagnostics as user validation; route missing persona inputs
into a rerun path, test plan, or acceptance question.
