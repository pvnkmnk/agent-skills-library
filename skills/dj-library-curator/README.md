# DJ Library Curator

Curates and maintains a high-quality DJ-ready music library from multiple sources, enforcing metadata hygiene, consistent folder structure, and crate organization for use in DJ software and Subsonic streaming.

## Quick Start

Invoke via your agent: `Invoke dj-library-curator` (OpenCode/Codex) or `/skill dj-library-curator` (Freebuff).

## What it does

- Scans and indexes music files across configured storage locations.
- Normalizes and enriches metadata: artist, title, release, genre, BPM, key, and comments.
- Applies DJ-focused tagging: energy level, mix-in/mix-out notes, and crate membership.
- Coordinates with `slskd-media-acquisition` and `subsonic-media-server` for acquisition and streaming integration.

## Inputs

- Library root paths and crate definitions.
- Target metadata schema and required fields.
- Source account/config for external services (e.g., Soulseek, Subsonic).

## Outputs

- Updated library with consistent metadata and folder structure.
- Crate/playlist definitions for DJ software.
- Reports on missing metadata, duplicates, or conflicts.

## Tooling & Dependencies

- Local filesystem access via homelab/media stack.
- Soulseek and Subsonic MCP/CLI clients for remote libraries.

## Failure Modes

- Incomplete or inconsistent metadata.
- Unreachable external services.
- Misaligned crate definitions vs. actual library contents.

## Companion Skills

`slskd-media-acquisition` · `music-library-organizer` · `dj-set-architect` · `subsonic-media-server`

See [SKILL.md](./SKILL.md) for the full canonical specification.
