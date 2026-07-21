# 0026: Identifier Scheme Remains Open

Status: Open

Date: 2026-07-21

## Context

Onbii objects need stable identifiers so relationships survive renaming, moving, syncing, and rendering through different applications.

Several identifier schemes could work, including UUIDs, ULIDs, content hashes, opaque IDs, or other structured identifiers.

## Decision

The requirement for stable identity is accepted, but the exact identifier scheme remains open.

## Consequences

- Linking documentation should describe identity requirements without choosing an ID format too early.
- Examples may use placeholder IDs.
- The final scheme should consider portability, privacy, readability, collision risk, and ease of implementation.
- This should be decided before stable bundle examples become normative.
