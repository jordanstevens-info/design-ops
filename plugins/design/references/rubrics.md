# Rubrics

Use rubrics to make evals useful without pretending every design judgment is
binary.

## Modes

Quick mode:

- Fast diagnostic loop
- Good for local iteration
- Can use current context
- Must label results as diagnostic

Smoke mode:

- Quick mode with a single smoke question
- Good for prototype, routing, and design-change checks
- Prefers fresh-context review when available
- Returns `Pass`, `Needs work`, or `Fail`
- Must not replace design acceptance or user validation

Thorough mode:

- Freezes input and output refs
- Captures artifact path, branch SHA, or source version
- Tracks contamination risk
- Prefers fresh-context review when quality matters
- Produces findings, evidence, confidence, and rerun instructions

Design-system eval mode:

- Uses acceptance scenarios as the primary review artifact
- Treats tokens, components, patterns, states, accessibility, and exceptions as
  contracts to evaluate against
- Can define missing scenarios before implementation or evaluate an existing
  output against them

Full eval reports use `templates/eval/eval-report.md` and should state evidence
quality, confidence, stop condition, and whether a feedback report is needed.
Smoke evals stay diagnostic and should not be treated as full acceptance.

## Common Dimensions

- Problem clarity
- User fit
- Design-system fit
- Accessibility
- Responsive behavior
- Interaction states
- Content clarity
- Implementation readiness
- Evidence quality
- Risk and reversibility

Extension lenses can add targeted questions to a rubric. Persona diagnostics are
a future lens, not user validation; do not invent personas when the persona
framework or team-specific battery is missing.

## Finding Shape

- Severity: critical, high, medium, low
- Evidence
- Impact
- Recommendation
- Blocking status
- Rerun instruction

Use lowercase pass/fail only for deterministic checks. Use `Pass`,
`Needs work`, or `Fail` only for diagnostic smoke eval verdicts. Use confidence
or severity for semantic design judgment.
