# 0001: Local-First Knowledge Ownership

Status: Accepted

Date: 2026-07-21

## Context

Onbii is intended for personal knowledge that may include conversations, recordings, notes, documents, media, and derived AI outputs. This material can be sensitive, long-lived, and personally or commercially important.

Existing products often keep captured knowledge inside a vendor application, hosted backend, or subscription service. That can make the knowledge harder to inspect, move, share on the user's terms, or preserve if the product changes.

## Decision

Onbii should be local-first and user-owned.

A useful Onbii archive should work from a user-controlled location such as a local folder, Obsidian vault, iCloud Drive, Dropbox, OneDrive, Nextcloud, Syncthing, Git, a NAS, or another chosen storage system.

Cloud services may provide sync, backup, collaboration, hosting, or processing, but they must not be the only place the knowledge can exist.

## Consequences

- Onbii should not require a proprietary backend to access an archive.
- Implementations should treat the user's storage as central.
- Sync and cloud support can exist, but should remain optional.
- Documentation should avoid presenting SaaS storage as the default ownership model.
- Machine indexes, databases, and caches should be rebuildable from the user's knowledge objects where practical.
