# docker-app-deployer

Handles end-to-end deployment of Docker and Docker Compose applications to homelab hosts — from pre-flight checks and environment variable injection through health verification and reverse proxy configuration.

## Quick Start

Invoke via your agent: `Invoke docker-app-deployer` (OpenCode/Codex) or `/skill docker-app-deployer` (Freebuff).

## What it does

- Runs a `homelab-safe-ops` pre-flight check and confirms target host disk space.
- Creates or validates `docker-compose.yml` / `Dockerfile`.
- Injects environment variables from `.env` or a secret manager — never hardcoded.
- Runs `docker compose pull` then `docker compose up -d`.
- Verifies the container is running and checks logs for errors.
- Invokes `reverse-proxy-and-tunnel` to configure external access if needed.
- Records the deployment event in `homelab-logbook`.

## Safety

- Credentials never hardcoded in compose files.
- Only named volumes used for persistent data — no anonymous volumes.
- No direct port exposure to the internet; always via reverse proxy or tunnel.
- Backup confirmed before replacing any container with persistent state.

## Dependencies

- Docker and Docker Compose on the target host
- `.env` or secret manager for environment variables

## Companion Skills

`homelab-safe-ops` · `reverse-proxy-and-tunnel` · `homelab-logbook` · `homelab-monitoring-analyst`

See [SKILL.md](./SKILL.md) for the full canonical specification.
