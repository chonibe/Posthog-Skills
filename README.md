# Posthog-Skills

Cursor (and compatible) **agent skills** for working with [PostHog](https://posthog.com).

## Skills

| Skill | Description |
|-------|-------------|
| [posthog-mcp-cursor](posthog-mcp-cursor/SKILL.md) | Use the official PostHog MCP from Cursor: flags, cohorts, insights, experiments, HogQL, errors, docs search, US/EU endpoints, and safe tool-calling habits. |

## Install (Cursor)

1. Clone this repo or copy a skill folder into your app repo, e.g. `.cursor/skills/posthog-mcp-cursor/` (must include `SKILL.md`).
2. Configure the PostHog MCP server in Cursor ([docs](https://posthog.com/docs/model-context-protocol/cursor.md)).
3. Reference the skill in chat (e.g. `@posthog-mcp-cursor`) or rely on description-based discovery.

## License

See [LICENSE](LICENSE).

## Contributing

Pull requests with additional PostHog-related skills (instrumentation, experiments, warehouse) are welcome; keep each skill self-contained with YAML frontmatter (`name`, `description`) on `SKILL.md`.
