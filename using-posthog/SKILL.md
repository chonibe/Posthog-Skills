---
name: using-posthog
description: Guides product analytics work with PostHog—events, person properties, cohorts, funnels, feature flags, session context, and EU vs US hosting. Use when the user asks about PostHog behavior, empty cohorts, funnel debugging, or syncing definitions. Optional PostHog MCP is used only for live schema and queries when the server is healthy, after reading tool schemas.
---

# Using PostHog

## When to use

- **Telemetry design**: event names, properties, person vs event properties, identify timing.
- **Cohorts and insights look wrong or empty** — check filter logic, person profile mode, and whether the app actually sends the properties the filters reference.
- **Region and API issues** — EU vs US hosts for ingest and REST API (401s often mean wrong region).
- **Automation** — scripts or CI that create/update cohorts, insights, or dashboards via the REST API.
- **Live inspection** — when PostHog MCP is configured, use it to read schema, run queries, and search docs; MCP is supplementary, not a substitute for correct client instrumentation.

## Core concepts

1. **Person profiles** — If cohorts use **person properties**, anonymous users need those properties stored. `person_profiles: "identified_only"` in `posthog-js` init skips full person behavior for anonymous visitors; use `always` (or PostHog’s current recommended setting) when person-property cohorts must include anonymous traffic.
2. **Session entry vs current path** — Properties that capture “first path in this tab” vs “current path” segment very differently. A cohort requiring “first path contains `/pricing`” will be much smaller than “ever viewed `/pricing`”.
3. **Definitions vs reality** — PostHog UI definitions can drift from git or from what the app emits. Prefer a single source of truth (e.g. exported filter JSON in repo) and PATCH/update via API or MCP when you change rules.
4. **EU / US** — Match `NEXT_PUBLIC_POSTHOG_HOST`, server-side API `POSTHOG_HOST`, and MCP base URL to the project’s region.

## Optional: PostHog MCP

- **When healthy**: explore `read-data-schema`, `event-definitions-list`, `query-run`, `docs-search`, cohort/flag tools, etc. Official catalog: [PostHog MCP](https://posthog.com/docs/model-context-protocol).
- **Always** read the tool’s JSON schema in your editor before calling; do not invent parameters.
- **When errored or absent**: use the PostHog web app and REST API; do not assume MCP succeeded.

## Troubleshooting (common)

| Symptom | Things to check |
|--------|------------------|
| Cohort size 0 | Filter too strict (entry path vs any activity); property never sent; typo in key; time window |
| Person cohorts fail for anonymous | `person_profiles` mode; missing `setPersonProperties` / capture payloads |
| REST 401 | Personal API key; **wrong regional host** (EU vs US) |
| MCP useless | Server disconnected; use API/UI instead |

## Workflow checklist

- [ ] Ingest host and API host match project region.
- [ ] Person profile mode matches cohort design.
- [ ] Event and property names in code match PostHog definitions.
- [ ] If MCP: healthy server → read schema → read-only queries before writes.

## Further reading

- [reference.md](reference.md) — MCP tool grouping, links, env vars.
