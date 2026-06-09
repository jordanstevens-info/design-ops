# Destination Policy

- Artifact:
- Recommended destination:
- User approval required:
- Destination approval source, if needed:
- Persistence expectation:
- Source of truth:
- Access requirements:
- Data class:
- Do not persist:
- External links:

## Defaults

- Output inline unless the user asks to persist, the workflow requires lineage,
  or the artifact will be reused.
- Ask before writing to external systems such as Figma, FigJam, Jira,
  Confluence, Slack, email, GitHub, GitLab, OneDrive, or cloud storage.
- Ask before pushing branches or making remote mutations.
- Keep source systems as source of truth when possible; link instead of copying.
- Do not persist C4, unknown possible-C4 material, credentials, secrets,
  private config, call recordings, or third-party IP without confirmed rights.
- For C3, persist only after the destination, access, and retention expectation
  are explicit.

## Common Destinations

- Inline response: default for small drafts, diagnostic checks, and accepted-only
  summaries.
- `.design/`: use for repo-backed branch context, reusable artifacts, changelog,
  demos, reports, and design-system or acceptance profiles.
- Figma or FigJam: use when the artifact is visual, collaborative, or native to
  the design canvas; requires user intent or approval.
- Jira or backlog: use for delivery tickets after scope and acceptance criteria
  are clear; draft inline before creating remotely.
- Confluence or docs: use for durable shared plans, reports, and decision
  records; draft inline before publishing.
- Slack or email: draft copy only; the user sends it.
- Git branch or MR: local branch work is allowed in engineering flows; push or
  remote MR actions require explicit approval.
