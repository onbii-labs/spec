# 0003: Bundles Over Loose Sidecar Files

Status: Accepted

Date: 2026-07-21

## Context

A knowledge object may contain several resources: content Markdown, original audio, transcripts, metadata, provenance, attachments, and derived outputs.

One possible representation is a loose group of related files:

```text
Meeting.md
Meeting.audio.opus
Meeting.transcript.json
Meeting.provenance.json
Meeting.photos/
```

That is understandable to engineers, but fragile for normal users. It is unclear which file to move, delete, sync, or back up. It also makes it easy to separate the source from the derived material.

## Decision

Onbii should prefer a bundle or package model for knowledge objects.

A bundle should appear as one manageable object to the user while remaining inspectable as ordinary files inside. The model is inspired by macOS bundles, but should not be macOS-only.

The specification should distinguish the logical knowledge object from any specific physical representation such as a directory package, ZIP package, platform bundle, cloud object, or future storage form.

## Consequences

- Users can move, copy, sync, back up, or delete one understandable object.
- Power users and developers can inspect internal files with ordinary tools.
- Small helpers such as Obsidian readers, Finder or Quick Look previews, tiny viewers, and CLI tools can expose useful facets without becoming the system of record.
- The exact `.onbii` package format remains to be specified.
- The bundle model should avoid returning to loose sidecar files as the normal user experience.
