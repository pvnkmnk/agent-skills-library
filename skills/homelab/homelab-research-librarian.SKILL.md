---
name: homelab-research-librarian
description: Teaches agents where and how to find reliable, high-signal homelab and self-hosting information.
category: homelab
tags: [homelab, research, documentation, self-hosting]
agents: [opencode, freebuff, antigravity, codex]
---

# homelab-research-librarian

## Purpose

Agents should not guess at homelab configurations. This skill teaches the correct search hierarchy for finding reliable, up-to-date homelab and self-hosting information.

## Invocation

**OpenCode / Codex:** `Invoke homelab-research-librarian`
**Freebuff:** `/skill homelab-research-librarian`

## Search Hierarchy

Always search in this order:

1. **Official vendor documentation** — always the primary source
   - Proxmox VE: https://pve.proxmox.com/wiki/Main_Page
   - TrueNAS: https://www.truenas.com/docs/
   - Traefik: https://doc.traefik.io/traefik/
   - Cloudflare Tunnel: https://developers.cloudflare.com/cloudflare-one/
   - Tailscale: https://tailscale.com/kb
   - Docker: https://docs.docker.com/
   - slskd: https://github.com/slskd/slskd/wiki
   - Subsonic/OpenSubsonic: https://subsonic.org/pages/api.jsp / https://opensubsonic.netlify.app

2. **High-signal community wikis and repos**
   - servarr wiki (Arr stack): https://wiki.servarr.com/
   - TRaSH Guides: https://trash-guides.info/
   - r/homelab wiki: https://www.reddit.com/r/homelab/wiki/index
   - r/selfhosted wiki: https://www.reddit.com/r/selfhosted/wiki/index
   - Awesome Self-Hosted: https://github.com/awesome-selfhosted/awesome-selfhosted

3. **Trusted community guides**
   - TechnoTim: https://technotim.live/
   - Wolfgang's channel notes
   - DB Tech notes
   - NetworkChuck for networking concepts

4. **Community forums (for edge cases / troubleshooting)**
   - Proxmox forums: https://forum.proxmox.com/
   - Reddit: r/homelab, r/selfhosted, r/proxmox, r/truenas
   - GitHub Issues on the specific project repo

## Rules

- Always cite the source when providing a configuration or command.
- Prefer docs and wikis over forum posts for initial guidance.
- Use community forums and Reddit only to cross-check edge cases or troubleshoot specific errors.
- Never present LLM-generated config as authoritative without cross-referencing official docs.
- If a piece of information cannot be found in official docs or trusted community guides, say so explicitly.

## Companion Skills

- `homelab-change-planner` — research before planning
- `homelab-topology-mapper` — research to understand your own environment
