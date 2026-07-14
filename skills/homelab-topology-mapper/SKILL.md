---
name: homelab-topology-mapper
description: Maps Proxmox cluster topology including nodes, VMs, containers, storage, and network layout.
---

# homelab-topology-mapper

Produces a current-state map of the Proxmox homelab cluster. Enumerates all nodes, VMs (QEMU), LXC containers, storage pools, and network bridges. Output is used as the starting context for any change operation.

## Invocation

**OpenCode / Codex:** `Invoke homelab-topology-mapper`
**Freebuff:** `/skill homelab-topology-mapper`

## Workflow Steps

1. **Connect:** Use `mcp/proxmox-mcp.json` to authenticate to Proxmox API.
2. **List nodes:** Enumerate all cluster nodes and their status.
3. **List VMs:** For each node, list all QEMU VMs (ID, name, status, CPU, RAM).
4. **List containers:** For each node, list all LXC containers (ID, name, status, CPU, RAM).
5. **List storage:** Enumerate storage pools with type, size, and usage.
6. **List networks:** Map network bridges and VLANs.
7. **Output:** Render topology as structured Markdown table.
8. **Store:** Optionally write snapshot to `obsidian-homelab-logbook`.

## Output Format

```
## Nodes
| Node | Status | CPU | RAM |

## VMs
| ID | Name | Node | Status | CPU | RAM |

## Containers
| ID | Name | Node | Status | CPU | RAM |

## Storage
| Name | Type | Size | Used |
```

## Companion Skills

- `homelab-change-planner` — use topology as pre-flight context
- `homelab-safe-ops` — always-on safety gate

## References

- Proxmox VE API: https://pve.proxmox.com/wiki/Proxmox_VE_API
- proxmox-mcp: https://github.com/canvrno/ProxmoxMCP
