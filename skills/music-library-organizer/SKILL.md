---
name: music-library-organizer
description: Import, tag, and organize music files using beets; enforce consistent folder structure, metadata, and MusicBrainz tagging across the local music library.
---

# music-library-organizer

## Purpose
Automate music file tagging and library organization using beets. Ingests raw downloads, applies MusicBrainz-backed metadata, enforces directory structure, deduplicates, and prepares files for streaming via Subsonic/Navidrome.

## Invocation
- "Organize new music downloads with beets"
- "Tag and import [artist/album] into library"
- "Fix missing tags in music library"
- "Deduplicate music library"
- "Run beets import on download folder"

## Workflow Steps
1. **Scan:** Identify new files in the slskd download directory (or configured inbox).
2. **Import:** Run `beet import -A` (auto-tag) against new files; apply MusicBrainz lookup.
3. **Review:** Flag low-confidence matches for manual review; log ambiguous items.
4. **Organize:** Move/copy files into the canonical library structure: `Library/Artist/Year - Album/Track - Title.ext`.
5. **Tag:** Apply standardized tags: artist, album, year, genre, MusicBrainz IDs, ReplayGain.
6. **Deduplicate:** Run `beet duplicates` and resolve conflicts (keep highest quality).
7. **Notify:** Signal `subsonic-media-server` to rescan library after import completes.
8. **Log:** Record import summary in `homelab-logbook`.

## Safety
- Never delete original files without explicit confirmation.
- Preserve original files in an inbox backup before moving.
- Do not overwrite manual tag edits without user approval.
- Validate file integrity (checksum) before and after move.

## MCP
- No dedicated MCP; invoked via shell commands or agent subprocess calls to `beet` CLI.
- Pairs with `slskd-mcp` for end-to-end acquisition-to-library pipeline.

## References
- beets documentation: https://beets.readthedocs.io/
- MusicBrainz: https://musicbrainz.org/
- beets GitHub: https://github.com/beetbox/beets

## Companion Skills
- `slskd-media-acquisition` — source of new music files
- `subsonic-media-server` — streaming target after organization
- `dj-library-curator` — curation layer on top of organized library
- `homelab-logbook` — import event logging
