# Communication Work

`/pd-slack-update` composes a copy-pasteable Slack update summarizing design work
across the current session. It gathers context from git, `.design/`, Figma,
Jira, Confluence, and other touched services when available.

Final authorship stays with the user. Never auto-publish through Slack, MCP
tools, messaging APIs, or webhooks.

## Gathering Context

Check each source in order. Skip any that do not apply.

### Git

Collect branch context:

```bash
git branch --show-current
git remote get-url origin
```

Check for structured change logs in priority order:

1. If `.design/changelog/` exists, read the most recent entry for this branch.
2. If `.design/artifacts/` or `.design/presos/` exists, scan for relevant
   additional context.
3. Else if `branch-log/changes/` exists, read the most recent entry for this
   branch.
4. Else if `branch-log/artifacts/` exists, scan for relevant context.
5. If none exist, fall back to commit history:

```bash
git log --oneline --no-merges HEAD...$(git merge-base HEAD main)
```

Derive the git hosting platform from the remote URL and construct branch or
compare URLs using standard GitHub or GitLab patterns.

### Figma

If Figma tools were used during the session, note which files or frames were
modified. Extract Figma URLs from tool context or responses.

### Jira and Product Tools

If Jira, Linear, or product-management tools were used, note which tickets were
created, updated, reviewed, or referenced. Extract issue URLs and ticket keys
from tool responses or `.design/changelog/`.

### Confluence

If Confluence tools were used, note which pages were created or updated and
include available page URLs.

### Other Services

If files were created or uploaded in SharePoint, OneDrive, Box, Drive, or other
services, note what was done and include available URLs.

### Change Log References

If `.design/changelog/` entries contain external references, include them in the
Links section. These entries are captured during `/pd-engineer` sessions and save
rediscovery.

### No External Tools

If only local file edits or git work occurred, focus the update on git context.
If no git work occurred and the session was purely Figma, Confluence, or product
tool work, skip branch info entirely.

## Branch Prefix Mapping

Derive emoji and category from the git branch prefix. If work spans multiple
tools and no single prefix fits, default to `:memo: Update`.

| Prefix | Emoji | Category |
|--------|-------|----------|
| `design/` | `:rainbow:` | Design |
| `feat/` | `:sparkles:` | Feature |
| `fix/` | `:wrench:` | Fix |
| `refactor/` | `:recycle:` | Refactor |
| `chore/` | `:broom:` | Chore |
| `docs/` | `:books:` | Docs |
| `plugin/` | `:claude:` | Plugin Dev |
| no prefix or unknown | `:memo:` | Update |

## Message Format

```markdown
**:<emoji>: <Category> - <Feature Name> (AB-1234)**

**Notes**
- <bullet 1>
- <bullet 2>

**Links**
- Branch: <branch URL>
- Ticket: <jira URL>
- Figma: <figma URL>
- Confluence: <confluence URL>
- Preso: <path or URL>
- Log: <log URL>
```

Only include link lines for sources that exist. The Links header is always
`**Links**`, not platform-specific.

If a Jira ticket is associated with the work, append the ticket key to the title
and include a Ticket link. Omit both if no ticket exists.

## Composing Each Section

| Section | How to Derive |
|---------|---------------|
| Emoji + Category | Use the branch prefix table. For multi-tool sessions without a clear git prefix, use `:memo: Update`. |
| Feature Name | Human-readable name from branch suffix, plan title, primary task, or design story topic. Strip hyphens/underscores and title-case. |
| Notes | Distill changelogs, git commits, and tool activity into casual first-person bullets. Focus on what changed and why it matters to the team, not implementation trivia. |
| Links | One line per touched source. Derive branch URLs from the remote. Use tool responses or changelog references for Figma, Jira, Confluence, and preso links. |

## Tone Guidance

- Write conversationally, not formally: "Added X", not "Implemented X
  functionality".
- Lead with what the team will see or notice.
- Flag requests for discussion or feedback explicitly.
- Include known limitations or follow-ups when they matter.
- Keep notes scannable: 3-7 bullets, no nested bullets.

## Fallbacks

| Scenario | Behavior |
|----------|----------|
| No `.design/changelog/` or `branch-log/changes/` directory | Derive notes from `git log`; omit Log link. |
| No git work | Skip branch info; use `:memo: Update`; derive notes from tool activity or user notes. |
| Unknown git host | Ask the user for the base URL before inventing links. |
| No links | Omit the Links section entirely. |

## Output Rule

Present the composed message inline with no prose before it. Do not wrap it in a
fenced code block. The output should be immediately readable, editable, and
copy-pasteable.

Never send the message through Slack or any messaging API. The user reviews,
edits, and decides when to share.
