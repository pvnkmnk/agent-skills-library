# Subsonic API Client

Integration guidance for consuming Subsonic/OpenSubsonic APIs in netrunner and other projects — covering client library selection, auth patterns, key usage patterns, and failure handling.

## Quick Start

Invoke via your agent: `Invoke subsonic-api-client` (OpenCode/Codex) or `/skill subsonic-api-client` (Freebuff).

## What it does

- Recommends client libraries (TypeScript `subsonic-api`, Python `libsonic`/`py-sonic`, Go patterns).
- Provides the canonical auth pattern using API keys from environment variables.
- Encodes netrunner-specific patterns: scan-before-query, exponential backoff, local metadata caching.
- Handles `error.code === 70` (file still scanning) gracefully.

## Dependencies

- Running Subsonic/OpenSubsonic server (e.g., Navidrome)
- `SUBSONIC_URL` and `SUBSONIC_API_KEY` in `.env`

## Companion Skills

`subsonic-media-server` · `netrunner-media-orchestrator`

See [SKILL.md](./SKILL.md) for the full canonical specification.
