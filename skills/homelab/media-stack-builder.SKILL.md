---
name: media-stack-builder
description: Scaffolds Docker Compose media stacks for pvnkmnk's homelab — slskd, Subsonic/OpenSubsonic, Jellyfin, reverse proxy, Watchtower.
category: homelab
tags: [homelab, docker, media, self-hosting, compose]
agents: [opencode, freebuff, antigravity, codex]
---

# media-stack-builder

## Purpose

Helps design and scaffold Docker Compose media stacks tailored to pvnkmnk's setup: slskd (Soulseek), Subsonic/OpenSubsonic-compatible servers (Navidrome, Airsonic-Advanced), Jellyfin, Glance dashboard, Watchtower, and a reverse proxy + tunnel layer.

## Invocation

**OpenCode / Codex:** `Invoke media-stack-builder`
**Freebuff:** `/skill media-stack-builder`

## Stack Components

### Acquisition layer
- **slskd** — headless Soulseek client (Docker: `slskd/slskd`)
  - Requires: shared dir, download dir, `slskd.yml` config
  - Expose via: reverse proxy only (not direct public port)
  - Auth: token-based, HTTPS enforced

### Media server layer (Subsonic API compatible)
- **Navidrome** (preferred for Subsonic/OpenSubsonic compatibility)
- **Airsonic-Advanced** (alternative)
- **Jellyfin** (for video + additional audio features)

### Dashboard
- **Glance** — lightweight homelab dashboard

### Maintenance
- **Watchtower** — automated container updates (set to notify-only or scheduled, not auto-pull on critical services)

### Networking layer
- Reverse proxy: Nginx Proxy Manager or Traefik
- Tunnel: Cloudflare Tunnel (preferred) or Tailscale
- DNS: Technitium or Pi-hole

## Compose Design Principles

1. Each service in its own named container with explicit restart policy.
2. All sensitive values in `.env` files, never hardcoded in `compose.yml`.
3. Named volumes for persistent data; bind mounts only for media directories.
4. Services networked via a shared internal Docker network; only the reverse proxy exposes ports to the host.
5. Labels on each container for reverse proxy autodiscovery (Traefik) or manual NPM config.

## Safety

- Never expose slskd or media server ports directly to the public internet.
- Apply `homelab-safe-ops` before deploying or modifying any compose stack.
- Use `homelab-change-planner` for any stack changes.

## References

- slskd: https://github.com/slskd/slskd
- Navidrome: https://www.navidrome.org/docs/installation/docker/
- Jellyfin: https://jellyfin.org/docs/general/installation/container/
- Watchtower: https://containrrr.dev/watchtower/
- TRaSH Guides: https://trash-guides.info/

## Companion Skills

- `homelab-safe-ops` — safety layer
- `reverse-proxy-and-tunnel` — networking layer
- `docker-app-deployer` — deployment patterns
- `slskd-media-acquisition` — slskd behavior
- `subsonic-media-server` — Subsonic/OpenSubsonic layer
