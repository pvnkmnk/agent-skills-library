# obsidian-music-journal

Creates and maintains music-related journal entries in Obsidian — listening sessions, DJ set plans, album reviews, curation session notes, and discovery logs, all linked into the vault knowledge graph.

## Quick Start

Invoke via your agent: `Invoke obsidian-music-journal` (OpenCode/Codex) or `/skill obsidian-music-journal` (Freebuff).

## What it does

- Classifies the note type: listening session, album review, DJ set plan, discovery note, or curation log.
- Loads the appropriate vault template (e.g., `templates/listening-session.md`, `templates/album-review.md`).
- Populates metadata: date, artist, album, genres, BPM/key (if DJ context), mood, rating, and notes.
- Adds wikilinks to related artist notes, genre MOCs, and previous sessions.
- Applies tags: `#music`, `#listening`, `#dj`, `#review`, etc.
- Saves the note to `Music Journal/YYYY/MM/` and updates the Music Journal index.

## Safety

- Never overwrites existing journal entries — always appends or creates new.
- Does not expose private session details in shared vault contexts.
- Confirms before deleting any journal note.

## Dependencies

- Obsidian vault with write access and a `Music Journal/` folder structure
- `mcp/obsidian-mcp.json` configured (Obsidian Local REST API)
- Optional: Obsidian Templater plugin for template execution

## Companion Skills

`obsidian-vault-manager` · `dj-library-curator` · `dj-set-architect` · `subsonic-media-server` · `homelab-logbook`

See [SKILL.md](./SKILL.md) for the full canonical specification.
