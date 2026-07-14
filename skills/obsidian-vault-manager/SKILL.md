---
name: obsidian-vault-manager
description: Create, organize, and maintain Obsidian vault notes, folders, and links; manage templates, daily notes, and vault structure via the Obsidian Local REST API or filesystem.
---

# obsidian-vault-manager

## Purpose
Provide agent-level control over an Obsidian vault: create and update notes, manage folder structure, apply templates, maintain internal links, and surface knowledge graph connections. Acts as the primary interface for all knowledge management tasks.

## Invocation
- "Create a note titled [title] in [folder]"
- "Update the note [path] with [content]"
- "List all notes in [folder]"
- "Find notes tagged with [tag]"
- "Create today's daily note"
- "Apply template [template-name] to new note"
- "Search vault for [query]"
- "Show backlinks for [note]"

## Workflow Steps
1. **Connect:** Establish connection to Obsidian Local REST API (port 27123) or target vault directory via filesystem.
2. **Locate:** Resolve target note or folder path within vault structure.
3. **Act:** Perform requested operation — create, read, update, delete, search, or list.
4. **Template:** Apply configured template if creating a new note in a templated folder.
5. **Link:** Ensure internal wikilinks are correct and bidirectional where applicable.
6. **Tag:** Apply relevant tags based on content type and folder context.
7. **Log:** Record significant vault changes in `homelab-logbook` if they affect key knowledge structures.

## Safety
- Never delete notes without explicit confirmation.
- Preserve existing content when updating — append or merge, do not overwrite unless instructed.
- Never expose vault credentials or API key in outputs.
- Respect vault folder structure conventions; do not create top-level folders without user direction.

## MCP
- **Obsidian Local REST API plugin** — provides REST endpoints for note CRUD, search, and metadata.
- Reference: https://github.com/coddingtonbear/obsidian-local-rest-api

## References
- Obsidian: https://obsidian.md/
- Obsidian Local REST API: https://github.com/coddingtonbear/obsidian-local-rest-api
- Obsidian community plugins: https://obsidian.md/plugins

## Companion Skills
- `obsidian-music-journal` — music-specific note creation
- `homelab-logbook` — homelab event logging to vault
- `homelab-research-librarian` — research note management
- `dj-set-architect` — writes set plans to vault
