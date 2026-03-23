# Posthog-Skills

Cursor (and compatible) **agent skills** for [PostHog](https://posthog.com) product analytics.

## Skills

| Skill | Description |
|-------|-------------|
| [using-posthog](using-posthog/SKILL.md) | Comprehensive, project-agnostic guidance: events, persons, cohorts, insights, flags, experiments, errors, warehouse, surveys, CDP, notebooks, LLM-related features, API automation, EU/US regions. Includes `references/` for domains, patterns, workflows, and MCP as **optional** enrichment (schema-first). Works without MCP. |

## Layout

`using-posthog/` contains `SKILL.md`, `reference.md` (index + external links), and `references/` for deeper progressive disclosure.

## Install (Cursor)

1. Copy the entire `using-posthog/` directory into your app repo, e.g. `.cursor/skills/using-posthog/`.
2. PostHog MCP is optional—in-editor queries when configured ([MCP + Cursor](https://posthog.com/docs/model-context-protocol/cursor.md)).
3. Use `@using-posthog` or rely on description-based discovery.

## License

See [LICENSE](LICENSE).

## Contributing

PRs welcome; keep YAML `name` and `description` on `SKILL.md`; add depth under `references/` rather than bloating the main file.
