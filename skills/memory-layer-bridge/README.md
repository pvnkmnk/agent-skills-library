# memory-layer-bridge

The always-on memory routing contract — tells agents when to query Mem0/Cipher, when to consult the Obsidian vault, and when to stay in the inline context window. Prevents duplicated retrieval, hallucinated past decisions, and lost session knowledge.

## Quick Start

Invoke via your agent: `Invoke memory-layer-bridge` (OpenCode/Codex) or `/skill memory-layer-bridge` (Freebuff).

This skill is **always-on** — active in every session.

## What it does

- Routes recall operations: past decisions/preferences → Mem0/Cipher; structured documents → Obsidian vault; session context → inline window.
- Routes writes: durable decisions and discoveries → Obsidian vault; user preferences/facts → also update Mem0.
- Homelab events → `obsidian-homelab-logbook` + `homelab-logbook`.
- Prevents duplicate logging across memory layers.
- Enforces ADR (Architecture Decision Record) logging for code architecture choices.
- Surfaces conflicting records across layers rather than silently picking one.

## Dependencies

- Mem0 or Cipher memory service (configured and reachable)
- Obsidian vault with Local REST API plugin enabled
- Optional: `obsidian-vault-manager` for structured vault writes

## Companion Skills

`obsidian-vault-manager` · `git-safe-ops` · `homelab-safe-ops` · `homelab-logbook` · `obsidian-homelab-logbook`

See [SKILL.md](./SKILL.md) for the full canonical specification.
