# PostHog MCP — reference

## Canonical documentation

- Full tool list, feature flags for URL filtering, pinning, and security notes: [Model Context Protocol (PostHog)](https://posthog.com/docs/model-context-protocol)
- Cursor-specific install: [Cursor](https://posthog.com/docs/model-context-protocol/cursor.md)
- Invoking tools via HTTP (advanced): [MCP tools API](https://posthog.com/docs/api/mcp-tools)

## Example agent prompts (from PostHog docs)

- Feature flags: e.g. create flag with rollout %; multivariate flags with integer percentages summing to 100.
- Analytics: trends, paths, funnels via `query-run` / `query-funnel` / `query-trends`.
- SQL/HogQL: `execute-sql` for system tables (e.g. feature flags metadata) and `events` analytics.
- Experiments: `experiment-create` with funnel-style metrics.
- Errors: `list-errors`, issue detail/update tools.
- Logs: `logs-query` with service/severity filters.

## Installing this skill in Cursor

Copy the folder `posthog-mcp-cursor/` (containing `SKILL.md`) into your project’s agent skills directory, for example:

- **Project skill:** `.cursor/skills/posthog-mcp-cursor/`  
- Or, if your team keeps a canonical `skills/` tree in-repo, place it at `skills/posthog-mcp-cursor/` and sync per your project’s docs.

Restart Cursor or reload the window if the skill does not appear. Ensure the [PostHog MCP server](https://posthog.com/docs/model-context-protocol) is configured and authenticated separately—this skill only documents how to use it safely.
