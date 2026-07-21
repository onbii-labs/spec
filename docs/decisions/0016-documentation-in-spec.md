# 0016: Documentation Lives In `spec` For Now

Status: Accepted

Date: 2026-07-21

## Context

At this stage Onbii has an idea, principles, an emerging object model, and a specification direction. It does not yet have a runtime, CLI, desktop app, mobile app, or stable reference implementation.

The project needs a clear place for vision, principles, roadmap, object model, bundles, linking, provenance, governance, and examples.

## Decision

Project documentation and specification work should live in the `spec` repository for now.

The specification does not start with schemas. It starts with why the specification exists and what design constraints it must preserve.

## Consequences

- `spec` is currently the project home.
- Vision, principles, roadmap, and explanatory docs can live alongside technical specification documents.
- A separate website can be added later when publishing needs justify it.
- Documentation should remain versioned Markdown in the repository.
