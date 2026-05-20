# Communication Work

`/slack-update` writes a copy-pasteable team update. Never auto-publish.

## Sources

Use available context in this order:

1. `.design/changelog/`
2. `.design/artifacts/` and `.design/presos/`
3. Current git branch and recent commits
4. Figma/Jira/Confluence links in user context
5. User notes

## Output

Use concise Slack-ready Markdown:

```markdown
**Design - <Topic>**

**Notes**
- <what changed or was learned>
- <what needs feedback>

**Links**
- Branch: <url>
- Ticket: <url>
- Figma: <url>
- Preso: <path or url>
```

Only include links that exist. The user decides whether to send it.
