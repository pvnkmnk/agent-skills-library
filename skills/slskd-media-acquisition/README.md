# slskd Media Acquisition

Provides an agent interface to slskd for discovering and downloading music from the Soulseek network — handles search, download queue management, transfer monitoring, and post-download handoff to the library pipeline.

## Quick Start

Invoke via your agent: `Invoke slskd-media-acquisition` (OpenCode/Codex) or `/skill slskd-media-acquisition` (Freebuff).

## What it does

- Connects to the slskd REST API (default: `http://localhost:5030`) using configured credentials.
- Submits search queries and returns results ranked by quality: FLAC > 320 kbps MP3 > lower bitrate.
- Enqueues user-approved files via the slskd `/transfers/downloads` endpoint.
- Monitors transfer status until completion; retries stalled or failed transfers.
- Hands downloaded files off to `music-library-organizer` for tagging and import.
- Records the acquisition event in `homelab-logbook`.

## Safety

- Requires `soulseek-network-orienter` invocation first (etiquette and rate limits).
- Only downloads files explicitly approved by the user.
- Validates file extensions before passing to the library pipeline (audio only).
- Maintains Soulseek community norms: respects share ratio and upload limits.

## Dependencies

- slskd instance running and accessible at configured URL
- `mcp/slskd-mcp.json` for MCP-based access, or slskd REST API credentials in env

## Companion Skills

`soulseek-network-orienter` · `music-library-organizer` · `subsonic-media-server` · `homelab-logbook`

See [SKILL.md](./SKILL.md) for the full canonical specification.
