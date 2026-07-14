---
name: dj-set-architect
description: Designs and sequences full DJ sets with arc planning, transition mapping, and energy flow analysis.
category: media
tags: [media, dj, set-design, transitions, energy-arc]
agents: [opencode, freebuff, antigravity, codex]
---

# dj-set-architect

## Purpose

Designs complete DJ sets from the ground up. Plans set arc (opener → peak → cooldown), maps transitions between tracks, checks key/BPM compatibility, and outputs a sequenced setlist with cue notes.

## Invocation

**OpenCode / Codex:** `Invoke dj-set-architect`
**Freebuff:** `/skill dj-set-architect`

## Workflow Steps

1. **Define context:** Venue type, duration, target energy profile.
2. **Select pool:** Pull candidate tracks from `dj-library-curator`.
3. **Sequence:** Arrange tracks for harmonic and energy flow.
4. **Map transitions:** Note mix points, loop opportunities, FX cues.
5. **Output:** Render ordered setlist as Markdown table with BPM/key columns.
6. **Save:** Log to `obsidian-music-journal` and `dj-mix-documentarian`.

## Safety

- Output is a planning document; no live system writes.
- Do not modify Subsonic playlists without explicit user approval.

## References

- [Mixed In Key](https://mixedinkey.com/)
- [DJ TechTools set planning](https://djtechtools.com/)

## Companion Skills

- `dj-library-curator`, `dj-mix-documentarian`, `music-project-planner`, `obsidian-music-journal`
