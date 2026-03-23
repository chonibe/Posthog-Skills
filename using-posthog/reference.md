# Using PostHog — reference

## Documentation

- [PostHog Model Context Protocol](https://posthog.com/docs/model-context-protocol) — MCP endpoints (US/EU), authentication, pinning, `?features=` tool subsets, security.
- [Cursor setup](https://posthog.com/docs/model-context-protocol/cursor.md)
- [Cohorts API](https://posthog.com/docs/api/cohorts)
- [posthog-js](https://posthog.com/docs/libraries/js) — init options including `person_profiles`

## Env vars (typical for API scripts)

| Variable | Role |
|----------|------|
| `POSTHOG_PERSONAL_API_KEY` | `phx_...` for REST management APIs |
| `POSTHOG_PROJECT_ID` | Project id |
| `POSTHOG_HOST` | Regional API base, e.g. `https://eu.i.posthog.com` |

## MCP tools (verify against live schema)

Grouped by purpose; exact names and args come from the MCP descriptor in your client:

| Area | Examples |
|------|-----------|
| Schema | `read-data-schema`, `event-definitions-list`, `properties-list` |
| Query | `query-run`, `query-trends`, `query-funnel`, `execute-sql` |
| Cohorts | `cohorts-list`, `cohorts-create`, `cohorts-partial-update`, … |
| Flags | `create-feature-flag`, `update-feature-flag`, `feature-flag-get-all`, … |
| Errors | `list-errors`, `error-details`, … |
| Docs | `docs-search` |

## Installing this skill

Copy `using-posthog/` (with `SKILL.md`) into `.cursor/skills/using-posthog/` in your project, or follow your team’s canonical `skills/` workflow.
