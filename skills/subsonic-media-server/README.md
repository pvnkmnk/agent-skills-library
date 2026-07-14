# subsonic-media-server

Provides agent-level control over a self-hosted Subsonic-compatible streaming server (Navidrome recommended) — playlist management, library rescan triggers, now-playing queries, and playback control via the OpenSubsonic REST API.

## Quick Start

Invoke via your agent: `Invoke subsonic-media-server` (OpenCode/Codex) or `/skill subsonic-media-server` (Freebuff).

## What it does

- Authenticates to the configured Subsonic server using token auth (`u=`, `t=`, `s=`, `v=`, `c=` params).
- Queries OpenSubsonic REST endpoints: getArtists, search3, getNowPlaying, getAlbumList, etc.
- Creates, updates, and deletes playlists.
- Triggers library rescans via `/rest/startScan` after new files are imported by `music-library-organizer`.
- Polls `/rest/getScanStatus` until the scan completes.
- Logs significant events (new content indexed, playlist changes) in `homelab-logbook`.

## Safety

- Never exposes Subsonic API credentials in logs or agent responses.
- Does not delete playlists or user data without explicit confirmation.
- Validates server reachability before bulk operations.

## Dependencies

- Navidrome or Airsonic instance running and accessible
- `mcp/subsonic-mcp.json` configured with server URL and credentials

## Companion Skills

`music-library-organizer` · `slskd-media-acquisition` · `dj-library-curator` · `media-stack-builder` · `homelab-logbook`

See [SKILL.md](./SKILL.md) for the full canonical specification.
