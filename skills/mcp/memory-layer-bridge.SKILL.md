---
name: memory-layer-bridge
description: Teaches agents when to query Cipher/Mem0, when to consult Obsidian, and when to use inline context — the routing layer for all persistent knowledge access. Always-on skill.
category: mcp
tags: [memory, obsidian, mem0, cipher, context, always-on, rag]
agents: [opencode, freebuff, antigravity, codex]
---

# memory-layer-bridge

## Purpose

Provides the routing contract for all persistent knowledge lookups. The agent stack has three distinct memory layers — each with different latency, scope, and retrieval semantics. This skill defines which layer to query first, under what conditions to escalate, and how to write new knowledge back to the correct store. This skill is **always-on** — active in every session.

## Invocation

**OpenCode / Codex:** `Invoke memory-layer-bridge`
**Freebuff:** `/skill memory-layer-bridge`

## Memory Layer Architecture

| Layer | Store | Best For | Access Pattern |
|---|---|---|---|
| **Semantic / Vector** | Cipher / Mem0 | Past decisions, user preferences, agent summaries, cross-session facts | Query via MCP or Cipher CLI |
| **Structured Knowledge** | Obsidian Vault | Long-form notes, project docs, homelab topology, music journal | Query via `obsidian-vault-manager` or Local REST API |
| **Inline Context** | Current session window | Active task state, working definitions, immediate conversation context | Already present — no query needed |

## Routing Rules

### When to query Cipher / Mem0 first
- User references a past decision, preference, or project without providing context.
- Agent needs to recall a specific fact established in a previous session.
- Task involves personalisation or user-specific configuration.

### When to query Obsidian first
- User references a note, project, or vault document by name.
- Task requires structured or long-form knowledge (homelab topology, music project plan, case notes).
- Lookup concerns a domain with dedicated vault folders (Homelab/, Music Journal/, Projects/).

### When to use inline context only
- All relevant information is present in the current session window.
- Task is short-lived and does not need to be persisted.
- No prior knowledge is being referenced.

### When to write back
- A significant decision is made → write a summary to Cipher / Mem0.
- A new note, plan, or log entry is created → write to Obsidian via `obsidian-vault-manager`.
- A preference or config fact is established → write to both layers for redundancy.

## Workflow Steps

1. **Classify the query:** Is it recalling a past fact, accessing structured docs, or operating on current context only?
2. **Route to the correct layer** using the rules above.
3. **Execute the lookup** via the appropriate tool (Cipher CLI, Obsidian REST API, or session context).
4. **Surface the result** with the source layer clearly attributed.
5. **Write back** new knowledge to the appropriate store before the session ends.

## Inputs

- User query or agent task description
- Available memory tools (Cipher/Mem0 MCP, Obsidian Local REST API)
- Current session context window

## Outputs

- Retrieved knowledge with source layer attribution (Cipher, Obsidian, or inline)
- Write-back confirmation if new knowledge was persisted
- Routing decision log (which layer was queried and why)

## Safety

- Never write sensitive credentials or API keys to any memory layer.
- Never conflate layers — a fact retrieved from Obsidian is not automatically in Cipher and vice versa.
- Always attribute the source layer when surfacing retrieved knowledge so the user can verify.

## Failure Modes

- **Cipher / Mem0 unavailable** — fall back to Obsidian, then inline context. Log that the vector layer was unavailable.
- **Obsidian vault not mounted** — fall back to inline context and notify the user that vault access is offline.
- **Conflicting facts across layers** — surface both versions to the user; do not silently pick one.
- **Write-back fails** — notify the user and provide the content to be stored manually.

## References

- Mem0 docs: https://docs.mem0.ai/
- Obsidian Local REST API: https://github.com/coddingtonbear/obsidian-local-rest-api
- Cipher (pvnkmnk internal): internal agent memory layer built on Mem0 + pgvector

## Companion Skills

- `obsidian-vault-manager` — primary interface for Obsidian layer writes and reads
- `homelab-safe-ops` — always-on safety layer
- `git-safe-ops` — always-on git safety layer
- `obsidian-homelab-logbook` — domain-specific Obsidian write target
- `obsidian-music-journal` — domain-specific Obsidian write target
