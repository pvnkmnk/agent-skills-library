---
name: music-library-organizer
description: Organizes downloaded music files into a structured, tagged library ready for Subsonic ingestion.
category: media
tags: [media, music, library, tagging, beets, file-structure]
agents: [opencode, freebuff, antigravity, codex]
---

# music-library-organizer

## Purpose

Automates the organization of raw music downloads into a coherent library structure. Handles tagging (via beets or equivalent), folder hierarchy normalization, duplicate detection, and prepares files for Subsonic/OpenSubsonic ingestion.

## Invocation

**OpenCode / Codex:** `Invoke music-library-organizer`
**Freebuff:** `/skill music-library-organizer`

## Workflow Steps

1. **Scan:** Identify target directory of unorganized downloads.
2. **Tag:** Run beets `beet import` or equivalent to fetch and apply metadata.
3. **Structure:** Move files to `Artist/Album/Track` hierarchy.
4. **Deduplicate:** Flag or remove exact duplicates by hash.
5. **Report:** Output a summary of files processed, tagged, moved, and flagged.
6. **Trigger rescan:** Notify `subsonic-media-server` to rescan the library path.

## Safety

- Never delete originals without explicit confirmation.
- Dry-run mode available; always offer before destructive moves.
- Log all operations to `obsidian-music-journal`.

## References

- [beets docs](https://beets.readthedocs.io/)
- [MusicBrainz API](https://musicbrainz.org/doc/MusicBrainz_API)

## Companion Skills

- `slskd-media-acquisition`, `subsonic-media-server`, `obsidian-music-journal`
