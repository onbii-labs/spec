# 0017: Avoid GitHub Wiki Initially

Status: Accepted

Date: 2026-07-21

## Context

GitHub Wiki was considered as a possible place for project documentation. The concern is that a wiki creates a second documentation location outside the normal repository review and versioning flow.

Onbii is an open specification project, so documentation should be reviewable, versioned, cloneable, and suitable for later website generation.

## Decision

Avoid GitHub Wiki initially.

Keep documentation as Markdown in the repository unless a specific need for a wiki appears later.

## Consequences

- Documentation changes can be reviewed through pull requests.
- Docs remain versioned with the specification.
- There is one obvious source of truth for project docs.
- A documentation website can later be generated from the repository.
