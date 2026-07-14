# Obsidian Vault Architect

Designs and enforces folder structure, naming conventions, template standards, tag taxonomy, and MOC placement for Obsidian vaults — the structural backbone that all other Obsidian-writing skills depend on.

## Quick Start

Invoke via your agent: `Invoke obsidian-vault-architect` (OpenCode/Codex) or `/skill obsidian-vault-architect` (Freebuff).

## What it does

- Audits the current vault structure and identifies inconsistencies.
- Proposes a folder hierarchy (PARA or custom: Inbox, Projects, Areas, Resources, Archive).
- Creates domain-specific note templates (music, homelab, daily log).
- Defines a canonical tag taxonomy, documented in `META/tags.md`.
- Creates or updates MOC (Map of Content) index notes per top-level domain.
- Produces a rename/move batch plan for existing notes — always requires user confirmation before execution.

## Safety

- Never deletes notes — only renames or moves with explicit user sign-off.
- Requires a vault backup before any structural changes.
- All changes are logged to a vault-change-log note.

## Dependencies

- Obsidian vault with write access
- Optional: Obsidian community plugins (Dataview, Templater) for advanced template execution

## Companion Skills

`obsidian-homelab-logbook` · `obsidian-music-journal` · `homelab-logbook`

See [SKILL.md](./SKILL.md) for the full canonical specification.
