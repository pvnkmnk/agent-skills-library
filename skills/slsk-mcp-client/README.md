# slsk MCP Client

Behavioral wrapper around the Slsk MCP server (MCPMarket) — adds safety rules, rate limiting, and session logging on top of the raw Soulseek MCP action layer.

## Quick Start

Invoke via your agent: `Invoke slsk-mcp-client` (OpenCode/Codex) or `/skill slsk-mcp-client` (Freebuff).

**Prerequisite:** Always invoke `soulseek-network-orienter` first.

## What it does

- Wraps `mcp/slsk-mcp.json` (Slsk MCP server from MCPMarket) with behavioral guardrails.
- Enforces a 1 search / 10 second rate limit with no automated loops.
- Requires explicit user approval before queuing any download.
- Logs every session to `obsidian-music-journal`.
- Keeps credentials strictly inside `mcp/slsk-mcp.json`.

## Dependencies

- Slsk MCP server configured at `mcp/slsk-mcp.json`
- Soulseek account credentials

## Companion Skills

`soulseek-network-orienter` · `slskd-media-acquisition` · `obsidian-music-journal`

See [SKILL.md](./SKILL.md) for the full canonical specification.
