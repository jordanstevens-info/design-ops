# Team Variants

The generic plugin is `design`. It should not know a host workspace system, a
company, a team, or a specific tool stack.

Team variants can use a prefix such as `<team>-design`, `alpha-design`, or
`studio-design`. They may add:

- team source maps and approved knowledge locations
- Jira, Confluence, Git, Figma, analytics, or research-tool defaults
- team design-system profiles and acceptance profiles
- product-specific templates, artifact examples, and workflow recipes
- approved vendors, data-policy mappings, and destination rules

A team variant can map Class 3 to approved source systems, allowed
destinations, design-system profile, Jira space, Figma library, and default
review owners. Keep those mappings in the variant, not the generic plugin.

Variants should extend the shared artifact-loop contracts instead of forking
them. If a generic rule needs to change for everyone, patch `design`. If a rule
only applies to a team, keep it in the team variant.
