# Design System Acceptance

Use this for eval, review, engineer, implementation-intent prototypes, and any
run that needs design-system fit.

Design system acceptance treats the design system as executable evals and
acceptance contracts. In generative design work, the system is stronger as a
set of tests to build toward than as a list of building blocks to avoid
disobeying. Tokens, components, and patterns are evidence and constraints; the
primary review artifact is the acceptance scenario.

```text
acceptance scenarios
-> build or generate
-> fixtures
-> checks
-> acceptance report
-> feedback or graduation
```

## Profile Selection

Select or infer:

- Design-system profile
- Maturity state: legacy, current, future, experimental, or project-born
- Acceptance mode: diagnostic, strict, migration-aware, or exploratory
- Applicable surfaces and fixtures
- Allowed exceptions

If no profile exists, say so and use exploratory guidance instead of pretending
strict acceptance is possible.

## Check Layers

- **Deterministic:** tokens, spacing, typography, contrast, component props,
  required states.
- **Structural:** composition, hierarchy, responsive behavior, loading/empty/error
  states, flow completeness.
- **Visual:** screenshot diffs, Storybook baselines, breakpoint comparison,
  Figma/code parity when available.
- **Semantic:** pattern fit, copy, density, hierarchy, and interaction fit.
- **Maturity/provenance:** conforming, migrating, extending, candidate pattern,
  or design debt.

## Acceptance Scenarios

Define acceptance scenarios before or during implementation when possible. Each
scenario should state:

- Scenario name
- Artifact surface
- User or job outcome
- State or breakpoint
- Design-system contract
- Evidence or check method
- Expected result
- Actual result, when evaluating an existing artifact
- Severity or blocking status
- Rerun instruction

Cover the primary path, important interaction states, responsive behavior,
loading/empty/error states when relevant, accessibility and focus behavior,
content edge cases, and exception or design-debt checks.

## Prototype Threshold

For rough exploratory prototypes, skip final design-system acceptance. Use the
system only to name future constraints.

For implementation-intent prototypes, select a profile and run exploratory or
strict acceptance based on maturity and risk.

## Acceptance Outcomes

- Accepted
- Accepted with required changes
- Needs design branch
- Needs user validation
- Needs problem or scope backfill
- Needs design-system exception
- Needs stakeholder decision
- Not ready

For MR-first acceptance, also include a merge recommendation:

- Ready for merge
- Approve with non-blocking design debt
- Block merge until required changes are made
- Request design branch before merge
- Needs formal decision owner or approver

## Exceptions And Debt

Design-system exceptions should state:

- Violated rule or profile
- Why the exception is needed
- Who approved or accepted the risk
- Blocking, temporary, permanent, or exploratory status
- Revisit trigger
- Whether it becomes a pattern candidate, backlog item, or design debt

Design debt should include artifact, issue, severity, owner, reason accepted,
revisit trigger, blocking status, and related report.

## Extension Lenses

Acceptance can use extension lenses such as accessibility, content quality,
implementation readiness, system performance, or future persona diagnostics.
Persona diagnostics are not user validation. The generic `design` plugin should
later provide tailorable persona primitives; team variants such as `fgt-design`
can add team-specific persona batteries and local evidence rules. Until those
inputs exist, do not invent personas.
