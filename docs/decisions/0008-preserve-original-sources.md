# 0008: Preserve Original Sources

Status: Accepted

Date: 2026-07-21

## Context

Onbii objects may include original audio, imported documents, photos, podcasts, voice memos, and other source material. Later tools may generate transcripts, summaries, classifications, links, embeddings, and other derivatives from those sources.

Generated outputs can improve over time. A lost source cannot be regenerated.

## Decision

Original source material should be preserved wherever practical.

For a recorded conversation, the audio is the source. For an imported document, the imported file is the source. For a photo, the original image is the source.

## Consequences

- Bundles should keep or reference source material clearly.
- Reprocessing should be possible when better tools or models appear.
- Derived artefacts should not replace the source.
- Storage and sync design must consider potentially large media files.
