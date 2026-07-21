# 0025: Exact `.onbii` Package Format Remains Open

Status: Open

Date: 2026-07-21

## Context

The bundle/package direction is accepted, but the physical representation is not yet specified.

Possible representations include a directory package, a ZIP-based package, a macOS bundle, a cloud object, a database row, or more than one supported representation.

## Decision

The exact `.onbii` package format remains open.

The project should define the logical knowledge object before prematurely locking down the storage container.

## Consequences

- `docs/BUNDLES.md` should remain illustrative until the format is specified.
- Examples can use a directory-style bundle for clarity.
- Cross-platform behaviour needs further design.
- The manifest format, required directory names, media handling, and sync semantics remain open.
