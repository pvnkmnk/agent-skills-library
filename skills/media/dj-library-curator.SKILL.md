---
name: dj-library-curator
description: Curates the DJ music library by building smart playlists, energy maps, and key/BPM collections.
category: media
tags: [media, dj, curation, playlists, bpm, key]
agents: [opencode, freebuff, antigravity, codex]
---

# dj-library-curator

## Purpose

Helps agents curate the DJ music library for mixing sessions. Builds playlists organized by BPM range, key, energy level, or genre. Interfaces with Subsonic API and DJ software exports (Rekordbox, Serato CSV).

## Invocation

**OpenCode / Codex:** `Invoke dj-library-curator`
**Freebuff:** `/skill dj-library-curator`

## Workflow Steps

1. **Query library:** Use `subsonic-api-client` to fetch tracks with metadata.
2. **Filter:** Apply user criteria (BPM range, key, genre, mood).
3. **Build playlist:** Assemble ordered tracklist, check harmonic compatibility.
4. **Export:** Generate M3U or Rekordbox XML export.
5. **Log:** Record playlist creation in `obsidian-music-journal`.

## Safety

- Read-only operations on library data; never delete tracks.
- Playlist exports are drafts; do not auto-publish to live systems.

## References

- [OpenSubsonic API](https://opensubsonic.netlify.app/)
- [Camelot Wheel / harmonic mixing](https://www.mixedinkey.com/harmonic-mixing-guide/)

## Companion Skills

- `subsonic-api-client`, `dj-set-architect`, `obsidian-music-journal`
