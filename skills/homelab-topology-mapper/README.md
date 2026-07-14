# homelab-topology-mapper

Produces a current-state map of the Proxmox homelab cluster — enumerates all nodes, VMs, LXC containers, storage pools, and network bridges as the pre-flight context for any change operation.

## Quick Start

Invoke via your agent: `Invoke homelab-topology-mapper` (OpenCode/Codex) or `/skill homelab-topology-mapper` (Freebuff).

## What it does

- Connects to the Proxmox API via `mcp/proxmox-mcp.json`.
- Lists all cluster nodes with status, CPU, and RAM.
- Lists all QEMU VMs and LXC containers per node with ID, name, status, and resources.
- Enumerates storage pools (type, size, usage) and network bridges/VLANs.
- Renders the full topology as a structured Markdown table.
- Optionally writes a snapshot to `obsidian-homelab-logbook` for historical tracking.

## Dependencies

- `mcp/proxmox-mcp.json` configured and Proxmox MCP server running
- Proxmox API credentials with read access

## Companion Skills

`homelab-change-planner` · `homelab-safe-ops`

See [SKILL.md](./SKILL.md) for the full canonical specification.
