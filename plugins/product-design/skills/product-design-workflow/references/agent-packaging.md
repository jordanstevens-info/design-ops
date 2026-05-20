# Agent Packaging

Claude and Codex agent assets use different formats.

## Claude Agents

Claude-facing agents are Markdown instruction files under:

```text
agents/claude/*.md
```

They are short role prompts. Long doctrine belongs in `references/agent-roles.md`
and workflow references, not in every agent file.

## Codex Agents

Codex custom agents are TOML files under:

```text
agents/codex/*.toml
```

Required fields:

```toml
name = "codebase_scout"
description = "Read-only repo discovery and compact project briefing."
developer_instructions = """
Stay in exploration mode. Detect repo structure, commands, docs, tokens,
components, and conventions. Do not edit files.
"""
```

Use kebab-case filenames and stable snake_case agent names.

Do not create Codex agent definitions as Markdown.
