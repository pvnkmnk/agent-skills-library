# Netrunner Media Orchestrator

The top-level orchestration skill for the netrunner media pipeline — coordinates acquisition, organization, serving, curation, and documentation across all media skills.

## Quick Start

Invoke via your agent: `Invoke netrunner-media-orchestrator` (OpenCode/Codex) or `/skill netrunner-media-orchestrator` (Freebuff).

## What it does

Orchestrates the full pipeline:

```
Soulseek → slskd/Slsk MCP → music-library-organizer → Subsonic/Navidrome → netrunner API → Obsidian vault
```

1. Define session goal (listening, DJ prep, curation, production).
2. Acquire music via Soulseek using `soulseek-network-orienter` + `slskd-media-acquisition` or `slsk-mcp-client`.
3. Organize downloaded files with `music-library-organizer`.
4. Trigger a Subsonic library rescan via `subsonic-media-server`.
5. Curate with `dj-library-curator` or journal with `music-listening-journal`.
6. Build sets with `dj-set-architect` or plan releases with `music-project-planner`.
7. Document everything to Obsidian via `obsidian-music-journal` and `dj-mix-documentarian`.

## Dependencies

- All child media skills configured and reachable
- Soulseek credentials, Subsonic URL/API key, Obsidian vault path

## Companion Skills

`soulseek-network-orienter` · `slskd-media-acquisition` · `slsk-mcp-client` · `subsonic-media-server` · `subsonic-api-client` · `music-library-organizer` · `dj-library-curator` · `dj-set-architect` · `obsidian-music-journal` · `dj-mix-documentarian`

See [SKILL.md](./SKILL.md) for the full canonical specification.
