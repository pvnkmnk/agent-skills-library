---
name: subsonic-media-server
description: Subsonic/OpenSubsonic auth, browsing, rescans, playlist management, and library hygiene.
category: media
tags: [media, subsonic, opensubsonic, navidrome, music-server]
agents: [opencode, freebuff, antigravity, codex]
---

# subsonic-media-server

## Purpose

Teaches agents to interact safely and correctly with Subsonic/OpenSubsonic-compatible media servers (Navidrome, Airsonic-Advanced, etc.) for browsing, rescans, playlist management, and library hygiene.

## Invocation

**OpenCode / Codex:** `Invoke subsonic-media-server`
**Freebuff:** `/skill subsonic-media-server`

## Authentication

OpenSubsonic supports two auth methods. Always prefer API keys:

**API Key (preferred):**
```
GET /rest/ping?u=<user>&apiKey=<key>&v=1.16.1&c=myapp&f=json
```

**Salted token (legacy fallback):**
```
token = md5(password + salt)
GET /rest/ping?u=<user>&t=<token>&s=<salt>&v=1.16.1&c=myapp&f=json
```

Never embed credentials in prompts. Reference from env variables or config files.

## Key Endpoints

| Endpoint | Purpose |
|---|---|
| `GET /rest/ping` | Health check |
| `GET /rest/getArtists` | List all artists |
| `GET /rest/getAlbumList2` | List albums |
| `GET /rest/search3` | Search library |
| `GET /rest/getPlaylists` | List playlists |
| `POST /rest/createPlaylist` | Create/update playlist |
| `GET /rest/startScan` | Trigger library rescan |
| `GET /rest/getScanStatus` | Check scan progress |

## Workflow

1. After new downloads from slskd, trigger `startScan`.
2. Wait for `getScanStatus` to confirm completion.
3. Verify new files appear in library with `search3` or `getAlbumList2`.
4. Organize playlists per context (listening, DJ prep, practice).
5. Report library stats to user.

## Companion Skills

- `slskd-media-acquisition` — acquisition before ingestion
- `music-library-organizer` — file organization before scan
- `subsonic-api-client` — client library integration for netrunner
- `netrunner-media-orchestrator` — full pipeline coordination

## References

- Subsonic API: https://subsonic.org/pages/api.jsp
- OpenSubsonic API: https://opensubsonic.netlify.app
- Navidrome: https://www.navidrome.org/docs/
