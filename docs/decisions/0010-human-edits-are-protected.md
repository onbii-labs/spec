# 0010: Human Edits Are Protected

Status: Accepted

Date: 2026-07-21

## Context

Onbii objects may be reprocessed as models improve. A newer transcription model may produce better text, a later speaker tool may improve attribution, or a new summariser may create better notes.

At the same time, a person may have corrected a transcript, renamed a speaker, added context, approved a summary, or rejected a suggested link.

## Decision

Human edits must be first-class and must not be silently overwritten by reprocessing.

Reprocessing may create a new version, revision, or proposed update, but it should preserve human corrections and approved content.

## Consequences

- Provenance should record human edits.
- Reprocessing workflows need versioning or proposal semantics.
- Human-approved material should be distinguishable from raw machine output.
- Implementations should avoid destructive regeneration by default.
