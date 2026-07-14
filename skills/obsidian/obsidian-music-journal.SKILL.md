---
name: obsidian-music-journal
description: The Obsidian vault layer for all music-related notes — listening logs, mixes, DJ sets, and artist research.
category: obsidian
tags: [obsidian, music, journal, vault, dj, listening]
agents: [opencode, freebuff, antigravity, codex]
---

# obsidian-music-journal

## Purpose

Serves as the central Obsidian knowledge hub for music. Manages the vault structure for music-related notes including listening sessions, mix documentation, DJ sets, artist/album research, and music project tracking. Acts as the write target for all music-domain skills.

## Invocation

**OpenCode / Codex:** `Invoke obsidian-music-journal`
**Freebuff:** `/skill obsidian-music-journal`

## Vault Structure

```
Music/
  Listening/       <- music-listening-journal entries
  Mixes/           <- dj-mix-documentarian entries
  Sets/            <- dj-set-architect plans
  Artists/         <- artist research notes
  Albums/          <- album review notes
  Projects/        <- music-project-planner entries
  MOC.md           <- music index
```

## Workflow Steps

1. **Route:** Determine which sub-section a write belongs to.
2. **Template:** Apply appropriate note template for the note type.
3. **Write:** Create or update note with provided content.
4. **Backlink:** Link to related artist, album, or project notes.
5. **Tag:** Apply canonical music tags.
6. **Update MOC:** Append entry to `Music/MOC.md` if it is a new entity.

## Safety

- Vault writes only; never modifies Subsonic or any live system.
- Never write passwords, API keys, or credentials to vault notes.

## References

- [Obsidian Help](https://help.obsidian.md/)

## Companion Skills

- `music-listening-journal`, `dj-mix-documentarian`, `dj-set-architect`, `music-project-planner`, `obsidian-vault-architect`
