---
name: dj-mix-documentarian
description: Documents completed DJ mixes with tracklists, timestamps, notes, and stores them in Obsidian.
category: media
tags: [media, dj, mix, documentation, obsidian, tracklist]
agents: [opencode, freebuff, antigravity, codex]
---

# dj-mix-documentarian

## Purpose

Captures post-mix documentation: full tracklist with timestamps, transitions notes, technical details (gear, software version), and context (event, venue, mood). Archives to Obsidian under a structured `Mixes` section.

## Invocation

**OpenCode / Codex:** `Invoke dj-mix-documentarian`
**Freebuff:** `/skill dj-mix-documentarian`

## Workflow Steps

1. **Input mix data:** Accept tracklist (manual or from export file), date, duration, venue/context.
2. **Enrich:** Pull BPM/key data for each track from `subsonic-api-client` or local cache.
3. **Format:** Build structured Markdown document with table of tracks + timestamps.
4. **Save:** Write to Obsidian vault under `Mixes/YYYY-MM-DD-mix-title.md`.
5. **Backlink:** Link each track to its artist page in the vault.
6. **Tag:** Apply event tags, vibe tags, and genre tags.

## Safety

- Writes only to Obsidian vault; no live system modifications.
- Never publish mix files externally without explicit user approval.

## References

- [Obsidian Markdown](https://help.obsidian.md/)

## Companion Skills

- `dj-set-architect`, `obsidian-music-journal`, `music-listening-journal`, `subsonic-api-client`
