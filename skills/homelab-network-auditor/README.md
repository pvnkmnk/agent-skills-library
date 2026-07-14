# homelab-network-auditor

Systematically audits the homelab network for open ports, exposed services, and firewall rule inconsistencies — produces an actionable security report and feeds findings directly into `homelab-change-planner`.

## Quick Start

Invoke via your agent: `Invoke homelab-network-auditor` (OpenCode/Codex) or `/skill homelab-network-auditor` (Freebuff).

**Safety first:** Always confirm scan scope with the user before running. Only scan infrastructure you own.

## What it does

- Defines scan scope (IP range, VLAN, or specific hosts) and requires user confirmation before proceeding.
- Runs host discovery (ping sweep or ARP scan) to enumerate active hosts.
- Executes a port scan (nmap or equivalent) and records open ports with service banners.
- Compares open ports against documented firewall rules and flags discrepancies.
- Identifies services reachable from the WAN interface that should not be.
- Produces a summary report: hosts scanned, open ports, unexpected exposures, and recommended remediations.
- Records audit results in `homelab-logbook` and creates remediation tasks in `homelab-change-planner`.

## Dependencies

- nmap or equivalent port scanner on the agent host
- Access to the homelab network from the scanning host
- Optional: `mcp/proxmox-mcp.json` for VM network inspection

## Companion Skills

`homelab-topology-mapper` · `homelab-safe-ops` · `homelab-change-planner` · `homelab-logbook` · `reverse-proxy-and-tunnel`

See [SKILL.md](./SKILL.md) for the full canonical specification.
