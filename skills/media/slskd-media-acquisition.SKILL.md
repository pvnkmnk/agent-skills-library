---
name: slskd-media-acquisition
description: Uses slskd web UI/API in homelab for targeted music acquisition via Soulseek.
category: media
tags: [media, soulseek, slskd, acquisition, homelab]
agents: [opencode, freebuff, antigravity, codex]
---

# slskd-media-acquisition

## Purpose

Teaches agents to use slskd (headless Soulseek client) safely as part of a homelab media acquisition workflow.

## Invocation

**OpenCode / Codex:** `Invoke slskd-media-acquisition`
**Freebuff:** `/skill slskd-media-acquisition`

Always invoke `soulseek-network-orienter` first to align with community etiquette.

## Prerequisites

- slskd installed (Docker: `slskd/slskd`) and configured:
  - Soulseek credentials in `slskd.yml`
  - Download and shared directories mounted
  - Token-based auth enabled
  - HTTPS enforced; reverse proxy configured
  - Access only via VPN or Cloudflare Tunnel remotely

## Workflow

1. Confirm slskd host URL and access method (LAN, Tailscale, Cloudflare Tunnel).
2. Invoke `soulseek-network-orienter` for etiquette context.
3. Plan targeted searches (artist, release, label, year).
4. Execute searches via slskd web UI or API.
5. Review results; present candidates to user for selection.
6. Queue approved downloads; monitor progress.
7. Post-download: coordinate with `music-library-organizer` and `subsonic-media-server`.
8. Log session to `obsidian-music-journal`.

## slskd API Reference

- API docs: served at `<slskd-host>/swagger`
- Key endpoints:
  - `POST /api/v0/searches` — initiate search
  - `GET /api/v0/searches/{id}/responses` — get results
  - `POST /api/v0/transfers/downloads/{username}/{filename}` — queue download
  - `GET /api/v0/transfers/downloads` — check queue
- Auth: `Authorization: Bearer <token>` header

## Safety

- Never expose slskd directly to the public internet.
- Never queue large batches without explicit user approval.
- Credentials and tokens stay in env/config files, never in conversation.

## References

- slskd docs: https://github.com/slskd/slskd/wiki
- slskd Docker: https://hub.docker.com/r/slskd/slskd
- slskd-mcp (OpenAPI → MCP): https://github.com/abl030/slskd-mcp

## Companion Skills

- `soulseek-network-orienter` — etiquette context (invoke first)
- `slsk-mcp-client` — MCP-based alternative
- `music-library-organizer` — post-download organization
- `subsonic-media-server` — ingest into media server
- `homelab-safe-ops` — always active
