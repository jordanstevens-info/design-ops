# System Performance

Use system-performance checks when improving the `design` plugin, a recipe, a
template, or a team variant. The product is a reflection of the system that made
it, so the system needs its own eval loop.

Unlike artifact evals, a system-performance eval scores the system that produced
the artifact: did the right skill trigger, did it follow the intended steps, and
was the output better than the prior version? Score the run, not just the final
artifact.

Ask:

- Was the right recipe or skill selected?
- Was the starting context sufficient and focused?
- Did the output improve the artifact or decision?
- Were findings and feedback actionable?
- Did the destination policy preserve useful lineage without storing excess
  context?
- Should a skill, recipe, template, profile, or variant rule change?

## Scenario Set

For recurring or comparable workflows, keep a durable scenario set rather than
judging from a single run. Use `templates/eval/skill-scenario-set.md`. Cover all
four invocation types so the eval catches both missed triggers and over-eager
false positives. Grow it from real misses; every fixed miss becomes a new row so
the regression cannot return silently.

Invocation types:

- **explicit:** names the skill directly; guards against name/description drift.
- **implicit:** describes the exact target scenario without naming the skill;
  tests whether the description alone selects it.
- **contextual:** adds realistic noise or domain context around the same need;
  tests selection under slightly messy prompts.
- **negative-control:** an adjacent request that must NOT trigger the skill;
  catches false positives and over-eager selection.

## Deterministic Checks vs Rubric Judgment

Separate the two signals and report them distinctly. Do not collapse a
deterministic miss into a soft quality note.

- **Deterministic checks** answer "did it do the basics?" and use lowercase
  pass/fail. Examples: the right skill triggered, expected steps or tool calls
  happened, required artifact sections or files were produced, no prohibited
  source was touched, the run stayed within intended permissions, and no
  unexpected files were left behind. Confirm each from a saved run transcript,
  log, or file state, not from recollection. If no such evidence exists, record
  the check as missing evidence rather than a pass; do not infer a pass.
- **Rubric judgment** answers "did it do it the way intended?" and uses
  confidence or severity, not pass/fail. Examples: output quality, finding
  usefulness, context fit, and whether the result advanced the decision.

A run can pass every deterministic check and still score low on rubric judgment;
report both separately.

## Baseline vs Candidate

Baseline-vs-candidate scoring applies only when evaluating a change to a skill,
recipe, template, or variant. For a single non-comparative run, the diagnostic
questions above are sufficient; do not manufacture a baseline.

When evaluating a change, score the prior version (baseline) and the new version
(candidate) over the same scenario set, then report the delta. Hold prompts,
evidence, and rubric constant across both so the difference is attributable to
the system change, not the inputs.
Name any deterministic check that regressed and any quality dimension that
moved. State whether the candidate should graduate, rerun, or roll back.

Use `templates/eval/system-performance-report.md` after demo runs, repeated
workflow misses, plugin smoke tests, or real runs that reveal a reusable
improvement.
