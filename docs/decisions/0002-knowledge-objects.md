# 0002: Knowledge Objects As The Primary Abstraction

Status: Accepted

Date: 2026-07-21

## Context

Early Onbii discussion considered Markdown notes, transcripts, audio files, sidecar JSON, graphs, and indexes. Markdown remains valuable because it is readable and durable, but a real captured item often contains more than one human-readable document.

A recorded conversation may include original audio, a transcript, speaker information, corrections, summaries, topics, links, provenance, attachments, and derived machine data.

Representing that as one Markdown file would either lose information or force too much machine-oriented structure into a human document.

## Decision

Onbii should model knowledge as objects.

A knowledge object is a self-contained unit of knowledge with stable identity, source material, human-readable representations, derived artefacts, provenance, metadata, and links.

Markdown is a first-class human-readable representation inside the object. It is not the whole object.

## Consequences

- The specification should define the object abstraction before locking down file layout details.
- Applications should treat Markdown, previews, graphs, transcripts, and AI recall as views or facets of the object.
- Object identity should not depend on filenames, note titles, or folder paths.
- The model can later support conversations, voice memos, podcasts, documents, photos, people, tasks, and other knowledge types without pretending they are all just notes.
