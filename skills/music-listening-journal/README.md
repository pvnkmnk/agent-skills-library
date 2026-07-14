# Music Listening Journal

Logs active listening sessions, albums, and tracks to Obsidian with ratings, notes, and discovery context — bridging Subsonic playback data with your vault knowledge base.

## Quick Start

Invoke via your agent: `Invoke music-listening-journal` (OpenCode/Codex) or `/skill music-listening-journal` (Freebuff).

## What it does

- Captures what you're listening to along with mood, activity, and discovery source.
- Applies a 1-5 star rating and brief review note.
- Tags entries with genre, decade, and vibe.
- Creates or appends to your Obsidian daily note under the `Music` heading.
- Backlinks to artist and album pages in the vault.

## Dependencies

- Obsidian vault with write access
- Optional: Subsonic/Navidrome `getNowPlaying` API for automatic track capture

## Companion Skills

`obsidian-music-journal` · `subsonic-api-client` · `dj-mix-documentarian`

See [SKILL.md](./SKILL.md) for the full canonical specification.
