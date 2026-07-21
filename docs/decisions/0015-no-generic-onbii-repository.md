# 0015: No Generic `onbii` Repository Yet

Status: Accepted

Date: 2026-07-21

## Context

The organisation is named Onbii. A repository named `onbii` would imply the whole project: macOS, Windows, Linux, mobile, CLI, SDK, APIs, plugins, adapters, sync, AI, and more.

The conversation considered a reference implementation, engine, SDK, parser, validator, CLI, and producer workflow, but no clear implementation boundary had been chosen.

## Decision

Do not create a generic `onbii` repository yet.

The organisation name should act as the umbrella. Repositories should have concrete responsibilities, such as `spec`, `adapters`, `website`, `cli`, `mobile`, `obsidian`, or `quicklook` when those boundaries become real.

## Consequences

- `spec` is the current home for the specification and project docs.
- Implementation repositories should be created only when their scope is clear.
- The first implementation should be driven by the first useful producer workflow, not by a placeholder repository name.
- A future monorepo is not ruled out, but it is not the current direction.
