# 0007: Applications Are Views

Status: Accepted

Date: 2026-07-21

## Context

Onbii should not become another application silo. The same knowledge object may be useful in Obsidian, Finder, Quick Look, a mobile app, a CLI, a search tool, a desktop viewer, or an AI recall surface.

The value is in user-owned knowledge that can outlive any one application.

## Decision

Applications should be views over Onbii knowledge objects.

An application may inspect, render, enrich, search, edit, preview, or sync objects, but it should not become the owner or only durable location of the knowledge.

## Consequences

- Small helpers and plugins are welcome when they expose objects.
- A full Onbii application should not be required before Onbii objects become useful.
- Obsidian, mobile, desktop, CLI, Quick Look, and AI chat can evolve independently.
- Documentation should distinguish the object from the views that render it.
