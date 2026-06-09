# Smoke Evals

Smoke evals are quick quality gates for local iteration. They are lighter than a
full eval loop and useful before spending more time on a prototype, design
change, artifact route, or acceptance pass.

Use a smoke eval when:

- a prototype needs a fast independent read
- a design change might have obvious acceptance issues
- a workflow route might be wrong
- a branch or MR needs a quick design-risk scan before deeper review
- an idea option needs a first-pass comparison

Do not use a smoke eval when:

- the source is known or suspected C4
- the decision needs real user validation
- the work requires formal approval
- the artifact is not stable enough to inspect
- a deterministic check or full acceptance review is already required

## Shape

```text
artifact or output
-> quick rubric
-> fresh-context reviewer when available
-> pass / needs work / fail
-> feedback report only if rerun constraints exist
-> next iteration
```

## Reviewer Context

When the host supports subagents or fresh-context reviewers, provide only:

- target artifact or diff
- expected user/job outcome
- relevant acceptance criteria
- relevant design-system profile or rubric
- highest known risk
- explicit data handling boundary

Do not include the primary agent's defense, intended fixes, or rationale. The
reviewer should inspect the artifact, not agree with the builder.

## Result Scale

- `Pass`: no blocking issue found for the smoke question.
- `Needs work`: issue found; rerun after targeted fix.
- `Fail`: wrong route, unsafe data handling, or artifact misses the intended
  outcome.

Smoke evals are diagnostic. They do not replace design acceptance, user
validation, accessibility testing, or formal approval.
