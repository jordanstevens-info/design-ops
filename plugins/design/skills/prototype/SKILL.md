---
name: prototype
description: >
  Create or revise coded prototypes, production facsimiles, option studies, or
  repo-backed prototype artifacts for learning and evaluation. Use for trying a
  flow or interaction before production commitment. Do not use for production
  code implementation, MR packaging, backlog ticket writing, design review, or
  processing C4 data.
---

# Prototype

Create a coded artifact for learning. It may be disposable, production-like, or
repo-backed.

Path resolution: resolve relative reference and template paths from the
directory containing this `SKILL.md`. If a host installs or exposes this skill
from a rewritten location, locate the nearest parent that contains both
`references/` and `templates/`, then resolve shared assets from that plugin
root.

Read:

- `../../references/artifact-loop.md`
- `../../references/data-handling.md`
- `../../references/eval-loop.md` when prototype output needs quick, full, or
  smoke eval routing
- `../../references/prototype-work.md`
- `../../references/resonant-frequency.md` when prototype options should test
  the project thread, decision rule, primary metric, or guardrail metrics
- `../../references/design-system-acceptance.md` when the prototype is
  implementation-intent or needs system-fit guidance
- `../../references/smoke-evals.md` when the prototype needs a fast diagnostic
  quality gate before more work
- `../../references/capability-discovery.md` when Figma, browser, Storybook, or
  local runtime access affects prototype verification
- `../../references/context-bootstrap.md` only in repo-backed mode
- `../../references/optional-delegation.md` only when comparing distinct
  prototype directions would help

Use templates:

- `../../templates/output/output-contract.md` for non-trivial outputs
- `../../templates/destination/destination-policy.md` before persisting or
  publishing prototype artifacts
- `../../templates/eval/smoke-eval-report.md` when running or requesting a
  quick prototype smoke eval
- `../../templates/eval/smoke-reviewer-prompt.md` when a fresh-context reviewer
  is available and useful

Mode rule:

- Explicit `--sandbox` means sandbox prototype.
- Explicit `--in-repo` means repo-backed prototype.
- If `.design/` exists, default to repo-backed.
- If app repo signals exist but `.design/` does not, ask sandbox or in-repo.
- If no repo/app signals exist, default to sandbox.

Always state the chosen mode and label fake data, shortcuts, missing states, and
production gaps. Use `../../templates/output/output-contract.md` for
non-trivial prototype output. Use a smoke eval when a fast independent read
would reduce iteration risk but a full eval loop is too heavy. When a resonant
frequency exists, state how the prototype will test or compare against it.
Produce a feedback report when the prototype exposes missing evidence, scope
backfill, validation needs, smoke eval findings, or rerun constraints. If source
material is known or suspected C4, stop as `Prohibited`; do not summarize,
quote, redact, transform, infer from, or generate from the source.
