---
type: Reference
title: "MCP Configuration Reference (Addy Osmani)"
tags: [mcp, configuration, claude-code, security, tools, integration]
timestamp: 2026-07-14
source: "LinkedIn Learning — Mastering AI-Assisted Development with Addy Osmani"
---

# MCP Configuration Reference (Addy Osmani)

Practical setup guide for Model Context Protocol — "USB for AI," an open standard
connecting AI tools to external systems (from *Mastering AI-Assisted Development*).

**Architecture:** AI tool (client: VS Code+Copilot/Cline, Claude Code, Cursor) → MCP
protocol → MCP server (lightweight local/remote adapter) → API/SDK → external service
(GitHub, PostgreSQL, Figma…).

**Config locations:** Claude Code global `~/.claude/settings.json`, project
`.claude/settings.json`; Cursor `.cursor/mcp.json`; VS Code `.vscode/mcp.json`.

**Server config shape** — each server under `mcpServers` gives a `command` (usually
`npx`), `args` (`-y @modelcontextprotocol/server-<name>`), and `env` (tokens/connection
strings). GitHub needs `GITHUB_PERSONAL_ACCESS_TOKEN` (repo scope min); Postgres needs a
`POSTGRES_CONNECTION_STRING`. Custom servers are built with `@modelcontextprotocol/sdk`
(`McpServer` + `StdioServerTransport`, register tools with `server.tool(...)`).

**Popular servers:** GitHub, PostgreSQL, MySQL, Filesystem, Puppeteer (browser),
Sentry, Slack, Linear/Jira.

**Security best practices:** read-only DB credentials (SELECT-only); keep credentials in
env vars, not committed config; `.gitignore` config files with secrets; never point MCP
at production DBs without restrictions; start read-only and add writes only with
confirmation; minimum token scopes.

**Troubleshooting:** restart the tool after config changes; verify token permissions on
auth errors; too many servers dilute context — start with one or two.

## Cross-links

The hands-on config layer for [Model Context Protocol (MCP) Architecture](mcp-architecture.md);
MCP is the "tool integration" layer of [Agent Harness Engineering](../harness-engineering/agent-harness-engineering.md)
and the "connectors" part of the [Loop Engineering Playbook](../harness-engineering/loop-engineering-playbook.md).
"Too many servers dilute context" echoes [CRESS](../harness-engineering/cress-context-checklist.md) (keep context small).

## References

- Course handout from *Mastering AI-Assisted Development* with Addy Osmani, on [LinkedIn Learning](https://www.linkedin.com/learning/) (paid course; PDF not stored — copyrighted material).
