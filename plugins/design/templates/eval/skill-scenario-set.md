# Skill Scenario Set

A durable, host-neutral prompt set for system-performance evals. Use it to check
whether a `design` skill, recipe, or template still triggers when it should,
stays quiet when it should not, and produces the intended artifact.

This is a blank starting form. It has little value on first creation; value
accrues only as real misses are recorded. Grow it as misses appear; every fixed
miss becomes a new row.

- Skill, recipe, or template under eval:
- Skill version or SHA:
- Host runtime:
- Owner:

## Scenarios

Cover at least one row of each invocation type (see
`references/system-performance.md` for invocation type definitions).
`should_trigger=false` rows are negative controls and are required.

| id | invocation | should_trigger | prompt | expected deterministic checks | expected rubric signal |
| --- | --- | --- | --- | --- | --- |
| s-01 | explicit | true | "Use the eval skill to run a system-performance eval of this change" | eval skill triggers; system-performance mode selected; report uses system-performance-report.md fields | high confidence the deterministic/rubric split is meaningful and the findings are actionable |
| s-02 | implicit | true | | | |
| s-03 | contextual | true | | | |
| s-04 | negative-control | false | "Review this MR for accessibility issues before we merge" | eval skill does not select system-performance mode; routes to design review or smoke eval instead | high confidence the request reads as artifact review, not a system or workflow eval |

## Data Handling

Use only Class 1 or Class 2 prompts in a stored scenario set. Never embed C4 or
unapproved third-party material in a fixture. If a real miss involves sensitive
input, record a sanitized stand-in and note the redaction.
