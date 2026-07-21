# 0004: Stable Identifiers Over Filenames

Status: Accepted

Date: 2026-07-21

## Context

Onbii objects need to link to conversations, people, projects, topics, documents, decisions, and other objects.

Human-readable filenames and titles are useful, but they change. A meeting may be renamed, moved to another folder, synced to another device, or displayed differently by another application.

Filename-based links, including familiar wiki-style links, are convenient but fragile as the durable relationship model.

## Decision

Onbii links should target stable object identities rather than filenames, paths, or display titles.

Applications may render those links as readable names, Markdown links, graph edges, timelines, previews, or search results. Users should not have to think in opaque IDs, but the durable relationship should not depend on a mutable label.

## Consequences

- Objects can be renamed or moved without breaking relationships.
- Obsidian and other tools may render friendly link views while Onbii preserves stable identity underneath.
- The identifier scheme is still open and should be specified later.
- Linking documentation should separate durable identity from user-facing display names.
