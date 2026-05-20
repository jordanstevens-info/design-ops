# Optional Delegation

`pd-workflow` does not package custom agents. The public plugin contract is
skills, references, and templates only. Delegation is an optional runtime
technique when the host supports subagents and the user has not disabled them.

Keep friction low. Do not require subagents to complete any workflow, and do
not block if delegation is unavailable.

## Review

Design review is the strongest case for delegation. A fresh-context reviewer can
avoid inheriting the primary agent's implementation rationale or attachment to
the work.

When useful, ask a subagent to inspect only:

- the target artifact or diff
- relevant acceptance criteria
- relevant design constraints
- known user goals

Do not include prior defense, intended fixes, or the primary agent's reasoning.
The delegated reviewer should return findings first, ordered by severity, with
missing evidence called out. The primary agent owns the final synthesis.

## Engineer

Delegation can help with read-only scouting while the primary agent works. Use
only for bounded discovery such as repo structure, commands, component/token
locations, existing docs, and relevant files.

Never delegate the blocking implementation path if the primary agent needs that
result before it can move.

## Prototype

Delegation can help compare distinct prototype directions or isolate a quick
facsimile exploration. Use it only when parallel exploration materially improves
the decision.

Prototype delegation must label fake data, shortcuts, missing states, and
production gaps.

## Artifact Skills

Do not use subagents by default for `scope`, `create-ticket`, `create-mr`,
`create-preso`, or `slack-update`. These are artifact synthesis workflows, and
delegation usually adds more process than value.
