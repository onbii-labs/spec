# 0009: Derived Data Is Not Truth

Status: Accepted

Date: 2026-07-21

## Context

AI and processing tools can produce useful transcripts, summaries, speaker labels, entities, topics, classifications, embeddings, and suggested links.

Those outputs are interpretations of source material. They may be wrong, incomplete, superseded by better tools, or changed by later context.

## Decision

Derived data should remain distinguishable from source material and human edits.

Generated outputs should carry provenance describing what created them, from which input, when, and where possible with which model, tool, or configuration.

## Consequences

- Transcripts, summaries, classifications, and links should record their origin.
- Machine-generated outputs can be regenerated or superseded.
- Users and applications should be able to tell whether a topic, link, or summary was human-set, imported, suggested, or derived.
- Graphs, indexes, vectors, and caches should not become the only durable record of meaning.
