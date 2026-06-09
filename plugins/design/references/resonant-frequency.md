# Resonant Frequency

Use this lens when design work needs a clearer throughline for scope,
prototypes, research, review, demos, or decision-making.

The resonant frequency is the qualitative signal that makes the work cohere.
Metrics translate that signal into design pressure so the team can compare
options without drifting into taste, solution bias, or polished ambiguity.

## Shape

```markdown
## Resonant Frequency

- Frequency:
- Signal:
- Why it matters:
- Primary metric:
- Supporting metrics:
- Guardrail metrics:
- Decision rule:
- Evidence:
- Open questions:
```

## Field Meaning

- **Frequency:** The short name for the project thread, such as speed through
  checkout, confidence choosing seats, time to diagnose, trust in data, reuse
  velocity, or decision clarity.
- **Signal:** The qualitative wavelength. What feels unresolved, painful,
  promising, slow, risky, unclear, or valuable?
- **Why it matters:** The user, product, team, business, or personal reason this
  thread deserves attention.
- **Primary metric:** The main quantitative target, when available.
- **Supporting metrics:** Secondary measurements that help explain movement.
- **Guardrail metrics:** Measurements that must not degrade while optimizing the
  primary metric.
- **Decision rule:** How to choose between viable options.
- **Evidence:** Source material, feedback, prototype results, analytics,
  research, or observed behavior supporting the frequency.
- **Open questions:** Gaps that could change the frequency, metrics, or
  decision rule.

## Workflow Rules

- If the frequency is known, carry it forward as the project thread.
- If the frequency is missing or contested on meaningful design work, treat that
  as a scope problem. Route to `scope` or `scope backfill` before pretending the
  work is ready for implementation, acceptance, or stakeholder packaging.
- If the work is small, tactical, or already tightly framed, use the lens
  lightly. Do not add ceremony when a short decision rule is enough.
- Jira/backlog tickets should consume the lens without exposing internal
  design-workflow lingo. Translate the frequency into outcomes, acceptance
  criteria, success metrics, constraints, or non-goals.
- Demos and presos should use the frequency as the story thread when the work
  needs stakeholder alignment.

## Example

```markdown
## Resonant Frequency

- Frequency: Speed through checkout
- Signal: The flow feels slower than it should, and each extra step creates more
  chances for hesitation or drop-off.
- Why it matters: Faster completion improves buyer experience and protects
  conversion.
- Primary metric: Median time from checkout start to order confirmation.
- Supporting metrics: p75 completion time, step abandonment, payment error
  recovery time.
- Guardrail metrics: Payment success rate, order accuracy, accessibility pass
  rate, support contacts.
- Decision rule: Prefer the option that reduces completion time unless it
  weakens trust, payment success, accuracy, or accessibility.
- Evidence: Stakeholder feedback, prototype timing, funnel drop-off by step.
- Open questions: Which step creates the most delay for returning buyers?
```
