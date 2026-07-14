# DJ Library Curator

This skill curates and maintains a high-quality DJ-ready music library from multiple sources (local files, Soulseek, Subsonic, etc.), enforcing metadata hygiene and library structure.

## Capabilities
- Scan and index music files across configured storage locations.
- Normalize and enrich metadata (artist, title, release, genre, BPM, key, comments).
- Apply DJ-focused tagging (energy level, mix-in/mix-out notes, crate membership).
- Coordinate with Soulseek and Subsonic skills for acquisition and streaming integration.

## Inputs
- Library root paths and crate definitions.
- Target metadata schema and required fields.
- Source account/config for external services (e.g., Soulseek, Subsonic).

## Outputs
- Updated library with consistent metadata and folder structure.
- Crate/playlist definitions for DJ software.
- Reports on missing metadata, duplicates, or conflicts.

## Tooling & Dependencies
- Local filesystem access via homelab/media stack.
- Soulseek and Subsonic MCP/CLI clients for remote libraries.

## Failure Modes
- Incomplete or inconsistent metadata.
- Unreachable external services.
- Misaligned crate definitions vs. actual library contents.
