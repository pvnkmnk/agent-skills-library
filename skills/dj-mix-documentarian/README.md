# DJ Mix Documentarian

Documents completed DJ mixes with full tracklists, timestamps, gear notes, and context, then archives them as structured notes in the Obsidian vault.

## Quick Start

Invoke via your agent: `Invoke dj-mix-documentarian` (OpenCode/Codex) or `/skill dj-mix-documentarian` (Freebuff).

## What it does

- Accepts a tracklist (manual or from a DJ software export) along with date, duration, and context.
- Enriches each track with BPM/key data from `subsonic-api-client` if available.
- Produces a Markdown document with a timestamped tracklist table.
- Saves the document to `Mixes/YYYY-MM-DD-mix-title.md` in your Obsidian vault.
- Backlinks each track to its artist page in the vault and applies event/vibe/genre tags.

## Dependencies

- Obsidian vault with write access
- `subsonic-api-client` for BPM/key enrichment (optional but recommended)

## Companion Skills

`dj-set-architect` · `obsidian-music-journal` · `music-listening-journal` · `subsonic-api-client`

See [SKILL.md](./SKILL.md) for the full canonical specification.
