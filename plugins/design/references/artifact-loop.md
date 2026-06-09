# Artifact Loop

Use this reference for every `design` workflow. The workflow scales around
artifacts, not phases.

```text
input artifact
-> workflow run
-> output artifact
-> eval or acceptance report
-> validation evidence when needed
-> feedback report
-> system-performance report when improving the workflow
-> next run
```

## Start Every Run

Classify the artifact before choosing a skill path:

- What artifact exists now?
- Who authored or last materially changed it?
- What decision is needed?
- What risk is highest?
- What evidence is missing?
- What data class applies?
- Which stop condition would end the run?

Entry modes:

- **Idea-first:** capture or park, scope, prototype options, eval, validation,
  ticket.
- **Build-first:** review, acceptance, feedback, engineer.
- **Prototype-first:** scope backfill, research plan, validation.
- **MR-first:** design-system acceptance, design review, MR feedback.
- **Post-launch-first:** analytics or research review, findings, scope.

## Recipe Registry

Recipes are reusable sequences. They are not public skill names.

Use these names in run manifests and reports:

| Recipe | Use when | Sequence |
|---|---|---|
| `idea-parking` | idea is worth saving but not acting on yet | `idea capture` |
| `idea-to-options` | idea needs exploration before commitment | `idea capture -> scope -> prototype -> eval -> feedback report` |
| `idea-to-research` | idea rests on an untested assumption | `idea capture -> research packet -> validation plan -> feedback report` |
| `idea-to-ticket` | idea or rough ask needs framing before delivery | `idea capture -> scope -> prototype -> eval -> validation -> jira-update` |
| `prototype-smoke-eval` | prototype needs a fast independent quality check before more work | `prototype -> smoke eval -> feedback report when needed` |
| `design-change-smoke-eval` | branch, Figma comp, or UI change needs a quick design-risk scan | `smoke eval -> review or engineer when needed` |
| `artifact-routing-smoke-eval` | workflow route may be wrong or evidence is ambiguous | `workflow -> smoke eval -> reroute or proceed` |
| `async-demo` | artifact needs one-way stakeholder walkthrough and feedback | `create-demo -> slack-update or feedback report when needed` |
| `build-to-acceptance` | built branch/MR needs design acceptance | `review -> design-system acceptance -> feedback report -> engineer or create-mr` |
| `prototype-to-validation` | prototype exists before requirements | `scope backfill -> research packet -> validation plan -> feedback report` |
| `mr-design-review` | MR/PR is ready for design review | `design-system acceptance -> design review -> MR feedback -> create-mr when requested` |
| `post-launch-redesign` | shipped UI or analytics evidence starts the run | `evidence review -> findings -> scope -> ticket or prototype` |

If no recipe fits, state `custom` and list the selected sequence.

## Recipe Step Mapping

Recipe steps map to skills, references, and templates:

| Step | Use |
|---|---|
| `idea capture` | `skills/workflow`, `references/ideas.md`, and `templates/ideas/idea-entry.md`; use `.design/ideas.md` only when repo-backed and a real entry exists |
| `scope` | `skills/scope` with `templates/scope/design-scope.md` |
| `scope backfill` | `skills/scope` with `templates/scope/scope-backfill.md` |
| `prototype` | `skills/prototype` |
| `eval` | `skills/eval`, `references/eval-loop.md`, `references/rubrics.md`, and `templates/eval/eval-report.md` |
| `smoke eval` | `skills/eval`, `references/smoke-evals.md`, `references/rubrics.md`, `templates/eval/smoke-eval-report.md`, and optional `templates/eval/smoke-reviewer-prompt.md` |
| `design-system acceptance` | `skills/eval` for explicit acceptance scenarios; `skills/review` for broader design critique or MR acceptance; use `references/design-system-acceptance.md` and `templates/acceptance/design-acceptance-report.md` |
| `design review` | `skills/review` |
| `MR feedback` | `skills/review` with merge recommendation and `templates/feedback/feedback-report.md` |
| `research packet` | `templates/research/research-packet.md` |
| `validation plan` | `templates/validation/validation-plan.md` |
| `validation findings` | `templates/validation/validation-findings.md` |
| `feedback report` | `templates/feedback/feedback-report.md` |
| `system-performance report` | `references/system-performance.md`, `templates/eval/system-performance-report.md`, and `templates/eval/skill-scenario-set.md` for scenario-set use |
| `engineer` | `skills/engineer` |
| `jira-update` | `skills/jira-update` |
| `create-mr` | `skills/create-mr` |
| `create-demo` | `skills/create-demo`, `references/demo-work.md`, and `templates/demo/` |

## Shared Output Fields

Use `templates/output/output-contract.md` when lineage is useful: persisted
artifacts, packages, reports, external destination updates, review/eval work,
system-performance work, or handoffs. Do not append it as a footer to inline
drafts or copy-pasteable messages.

When useful for the artifact, include:

- Entry mode
- Source refs or context used
- Data handling decision
- Destination
- Output artifact
- Artifact author
- Workflow runner
- Design reviewer
- Technical reviewer
- Decision owner
- Formal approver, if applicable
- Evidence reviewed
- Missing evidence
- Stop condition
- Feedback report or rerun instruction

Stop conditions:

- Accepted
- Accepted with required changes
- Rerun
- Needs human decision
- Needs evidence
- Blocked
- Prohibited
- Not worth continuing
- Graduate

## Feedback Report

Feedback reports turn findings into next-run constraints. Produce a standalone
feedback report whenever a run ends with `Accepted with required changes`,
`Rerun`, `Needs human decision`, `Needs evidence`, `Blocked`, `Prohibited`,
`Not worth continuing`, or `Graduate`. For tiny accepted-only work, a short
inline summary is enough.

Minimum shape:

- Source: eval, validation, stakeholder, user, designer, engineer, product, or
  system
- Subject: artifact, workflow, project, skill, template, or system
- Decision: keep, change, rerun, drop, escalate, or graduate
- Constraints for next run
- Required evidence
- Open questions
- Destination or owner
- Status

## Run Lineage

For non-trivial runs, preserve lineage:

- Input artifact refs
- Output artifact refs
- Template, rubric, profile, or recipe refs
- Tools used
- Decisions made
- Feedback report refs
- Prompt, output, and change records when policy requires them

Keep lineage lightweight. Link to source systems instead of copying sensitive
source material into local files.

## Destination

Use `templates/destination/destination-policy.md` before persisting or
publishing artifacts. Default to inline output unless the user asks to persist,
lineage is needed, or the artifact will be reused. External systems and remote
mutations require explicit approval.
