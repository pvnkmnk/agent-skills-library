# obsidian-vault-manager

The primary agent interface for Obsidian vault operations — creates and updates notes, manages folder structure, applies templates, maintains internal wikilinks, and surfaces knowledge graph connections via the Obsidian Local REST API.

## Quick Start

Invoke via your agent: `Invoke obsidian-vault-manager` (OpenCode/Codex) or `/skill obsidian-vault-manager` (Freebuff).

## What it does

- Connects to the Obsidian Local REST API (port 27123) or the vault directory via filesystem.
- Resolves target note or folder paths within the vault structure.
- Creates, reads, updates, searches, and lists notes and folders.
- Applies configured templates when creating notes in templated folders.
- Ensures internal wikilinks are correct and bidirectional where applicable.
- Applies tags based on content type and folder context.
- Logs significant vault changes to `homelab-logbook` when they affect key knowledge structures.

## Safety

- Never deletes notes without explicit confirmation.
- Appends or merges when updating — never overwrites unless explicitly instructed.
- Never exposes vault API key in outputs.
- Does not create top-level folders without user direction.

## Dependencies

- Obsidian with the Local REST API plugin enabled and running
- `mcp/obsidian-mcp.json` configured with vault URL and API key

## Companion Skills

`obsidian-music-journal` · `homelab-logbook` · `homelab-research-librarian` · `dj-set-architect`

See [SKILL.md](./SKILL.md) for the full canonical specification.
