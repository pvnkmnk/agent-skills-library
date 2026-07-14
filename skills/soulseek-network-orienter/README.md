# Soulseek Network Orienter

Orients agents and users to Soulseek's culture, etiquette, and search strategies for respectful, intentional music discovery and acquisition. Always invoke this before any Soulseek MCP tools or slskd API calls.

## Quick Start

Invoke via your agent: `Invoke soulseek-network-orienter` (OpenCode/Codex) or `/skill soulseek-network-orienter` (Freebuff).

## What it does

- Reminds the agent of Soulseek community norms: share ratio, queue patience, bandwidth respect.
- Proposes targeted search strategies (artist, label, year, scene keywords, FLAC-first).
- Clarifies user intent and produces recommended search terms.
- Coordinates handoff to `slskd-media-acquisition` or `slsk-mcp-client` for downloads.
- Logs discovered music to `obsidian-music-journal`.

## Dependencies

- Soulseek account (via slskd or Soulseek Qt)
- Obsidian vault for discovery logging

## Companion Skills

`slskd-media-acquisition` · `slsk-mcp-client` · `obsidian-music-journal` · `music-library-organizer`

See [SKILL.md](./SKILL.md) for the full canonical specification.
