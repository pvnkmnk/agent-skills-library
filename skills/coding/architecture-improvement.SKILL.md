---
name: architecture-improvement
description: Reviews and proposes improvements to system architecture — module boundaries, coupling, cohesion, data flow, and scalability — with a structured ADR output.
category: coding
tags: [coding, architecture, design, adr, refactor, systems]
agents: [opencode, freebuff, antigravity, codex]
---

# architecture-improvement

## Purpose

Systematically reviews existing system architecture to identify coupling, missing abstractions, scalability bottlenecks, and violated design principles. Produces an Architecture Decision Record (ADR) for proposed improvements.

## Invocation

**OpenCode / Codex:** `Invoke architecture-improvement`
**Freebuff:** `/skill architecture-improvement`

## Review Dimensions

- **Coupling:** Are modules too tightly coupled? Can they be changed independently?
- **Cohesion:** Does each module have a single, clear responsibility?
- **Data flow:** Is the data flow clear and directional, or spaghetti?
- **Boundaries:** Are domain boundaries well-defined and respected?
- **Scalability:** Where are the bottlenecks under load?
- **Testability:** Can each module be unit-tested in isolation?

## ADR Output Structure

```markdown
# ADR: <title>
Date: YYYY-MM-DD
Status: Proposed

## Context
<current architecture and its problems>

## Decision
<proposed change>

## Rationale
<why this is better>

## Consequences
<trade-offs and risks>

## Alternatives Considered
<other options and why rejected>
```

## Inputs

- Codebase or module description
- Existing architecture diagram (if any)
- Pain points or performance issues observed

## Outputs

- Architecture review report with findings per dimension
- One or more ADRs for proposed improvements
- Prioritised list of changes (quick wins vs. large refactors)

## Failure Modes

- **Codebase too large to review in full** — focus on the module or pain point specified; don’t attempt a full-system audit without scoping.

## Companion Skills

- `refactor-with-tests` — implement the proposed changes safely
- `grill-me` — stress-test the proposed architecture before committing to it
