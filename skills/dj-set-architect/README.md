# dj-set-architect

Designs and sequences DJ sets using harmonic mixing principles, BPM flow analysis, and energy curve planning — generates structured set plans and tracklists from the curated DJ library and archives them to Obsidian.

## Quick Start

Invoke via your agent: `Invoke dj-set-architect` (OpenCode/Codex) or `/skill dj-set-architect` (Freebuff).

## What it does

- Takes target duration, genre, BPM range, and energy curve shape (build, peak, cool-down).
- Queries `dj-library-curator` crates for candidate tracks matching the parameters.
- Flags un-analyzed tracks (no BPM/key) and routes them for analysis.
- Applies Camelot Wheel harmonic mixing rules to build a compatible sequence.
- Presents a draft tracklist with BPM, key, and transition notes for user review.
- Accepts edits to swap or reorder tracks.
- Exports the set as an M3U playlist and optionally pushes it to `subsonic-media-server`.
- Saves the set plan to `obsidian-music-journal` as a structured note.

## Dependencies

- `dj-library-curator` with BPM/key-analyzed crates
- Optional: `subsonic-mcp` for M3U playlist output; `mcp/obsidian-mcp.json` for set plan notes

## Companion Skills

`dj-library-curator` · `subsonic-media-server` · `obsidian-music-journal` · `homelab-logbook`

See [SKILL.md](./SKILL.md) for the full canonical specification.
