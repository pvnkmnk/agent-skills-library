# homelab-safe-ops

The always-on safety contract for all homelab automation — enforces read-before-write discipline, blocks destructive operations without explicit confirmation, and keeps credentials out of prompts. Active in every session that touches infrastructure.

## Quick Start

Invoke via your agent: `Invoke homelab-safe-ops` (OpenCode/Codex) or `/skill homelab-safe-ops` (Freebuff).

This skill is **always-on** — load it at the start of every homelab session.

## What it does

- Requires reading current state (running services, configs, mounted volumes) before modifying anything.
- Blocks deletion, stopping, or removal of any resource not explicitly named by the user.
- Pauses and confirms before any irreversible action (delete, format, wipe, stop service).
- Prevents direct port exposure to the internet — requires Cloudflare Tunnel, WireGuard, or Tailscale.
- Keeps credentials out of conversation text — references env files or secret managers only.
- Requires backup confirmation before any data migration or storage operation.
- Requires staging test (if available) before applying changes to production.
- Escalates to user if an operation would affect more than one service at once.

## Dependencies

- Any homelab environment (Proxmox, Docker, LXC, bare metal)
- Pairs with `homelab-change-planner` for planned changes, `homelab-logbook` for logging

## Companion Skills

`homelab-change-planner` · `homelab-logbook` · `homelab-topology-mapper` · `reverse-proxy-and-tunnel`

See [SKILL.md](./SKILL.md) for the full canonical specification.
