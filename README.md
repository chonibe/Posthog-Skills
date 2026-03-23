# Posthog-Skills

Cursor (and compatible) **agent skills** for [PostHog](https://posthog.com) product analytics.

## Skills

| Skill | Description |
|-------|-------------|
| [using-posthog](using-posthog/SKILL.md) | Events, person properties, cohorts, EU/US hosts, troubleshooting; PostHog MCP only as optional live inspection with schema-first tool use. |

## Install (Cursor)

1. Copy `using-posthog/` into your app repo, e.g. `.cursor/skills/using-posthog/` (include `SKILL.md`).
2. Configure PostHog MCP if you want in-editor queries ([docs](https://posthog.com/docs/model-context-protocol/cursor.md)); the skill is useful without MCP.
3. Reference with `@using-posthog` or rely on description-based discovery.

## License

See [LICENSE](LICENSE).

## Contributing

PRs welcome; each skill stays self-contained with YAML `name` and `description` on `SKILL.md`.
