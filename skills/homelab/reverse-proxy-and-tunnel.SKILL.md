---
name: reverse-proxy-and-tunnel
description: Securely exposes homelab services via Traefik/NPM/Caddy + Cloudflare Tunnel/WireGuard/Tailscale.
category: homelab
tags: [homelab, networking, reverse-proxy, tunnel, vpn, security]
agents: [opencode, freebuff, antigravity, codex]
---

# reverse-proxy-and-tunnel

## Purpose

Teaches agents the correct, safe patterns for exposing homelab services externally — using reverse proxies and tunnels rather than direct port forwarding.

## Invocation

**OpenCode / Codex:** `Invoke reverse-proxy-and-tunnel`
**Freebuff:** `/skill reverse-proxy-and-tunnel`

## Exposure Hierarchy (most to least preferred)

1. **Cloudflare Tunnel** — zero-port-forward, encrypted, DDoS-protected. Best for public-facing services.
2. **Tailscale** — mesh VPN for private access across devices without open ports. Best for personal access.
3. **WireGuard** — self-hosted VPN for LAN extension. Use when Tailscale is not suitable.
4. **Reverse proxy + firewall** — only if a tunnel is not viable; always with strict firewall rules and fail2ban/CrowdSec.

**Never use direct port-forwarding without a reverse proxy and strong firewall rules.**

## Reverse Proxy Options

- **Nginx Proxy Manager (NPM)** — GUI-driven, easiest for most cases
- **Traefik** — Docker-label-driven autodiscovery, ideal for dynamic container environments
- **Caddy** — automatic HTTPS, simple config, good for static setups

## Security Checklist

- [ ] HTTPS/TLS on all exposed services (Let's Encrypt or Cloudflare-issued)
- [ ] Cloudflare proxied DNS (orange cloud) for all public-facing domains
- [ ] fail2ban or CrowdSec on the host
- [ ] Authelia or Authentik for SSO on sensitive services
- [ ] Geo-blocking or IP allowlisting where possible
- [ ] No plain HTTP in production
- [ ] Rate limiting on auth endpoints

## Companion Skills

- `homelab-safe-ops` — always active
- `media-stack-builder` — exposes media services safely
- `docker-app-deployer` — container networking patterns

## References

- Cloudflare Tunnel: https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/
- NPM: https://nginxproxymanager.com/
- Traefik: https://doc.traefik.io/traefik/
- Tailscale: https://tailscale.com/kb
- CrowdSec: https://www.crowdsec.net/
