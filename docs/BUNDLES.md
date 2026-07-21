# Bundles

Onbii defines a bundle model to keep knowledge objects manageable, portable, and inspectable.

A bundle is a package that appears to the user as one object while containing ordinary files inside. It is inspired by macOS bundles, but it is an Onbii concept rather than a macOS-only feature.

## Why Bundles

Loose sidecar files are fragile.

A meeting represented as separate files can quickly become confusing:

```text
Meeting.md
Meeting.audio.opus
Meeting.transcript.json
Meeting.entities.json
Meeting.provenance.json
Meeting.photos/
```

An engineer may understand that these files belong together. A normal user may not. They may move the Markdown file and leave the audio behind, delete a JSON file that looked unimportant, or break sync by treating one object as many unrelated files.

Onbii should avoid that failure mode.

## One Thing To The User

A bundle lets the user handle one thing:

```text
2026-07-21 Meeting with Jean-Paul.onbii
```

The user should be able to move it, copy it, back it up, sync it, or delete it as one object.

Inside, it may contain many resources:

```text
2026-07-21 Meeting with Jean-Paul.onbii/
  manifest.yaml
  content.md
  source/
    recording.m4a
  derived/
    transcript.json
    transcript.md
    summary.md
    speakers.json
  attachments/
```

This internal layout is illustrative. The exact bundle format has not yet been specified.

## Inspectable By Design

Bundles should hide complexity without hiding the user's knowledge.

A normal user sees one object. A power user can inspect the contents. A developer can parse it using documented formats and ordinary tools.

The bundle should not require a proprietary database or hosted service to be understood.

## Cross-Platform

Onbii bundles should not depend on macOS.

On macOS, a `.onbii` bundle may behave like a package in Finder. On other platforms, the same object may appear as a directory, archive, or another documented representation. The goal is to preserve the same logical object across platforms, not to make every platform imitate Finder.

The specification should distinguish:

- the logical Onbii object;
- the bundle or package representation;
- platform-specific presentation.

## Manifest

The manifest is the anchor of the bundle.

It should describe the object and its resources explicitly rather than relying on filename conventions. It should contain or reference:

- object identity;
- object type;
- schema version;
- title or display name;
- source material;
- human-readable representations;
- derived artefacts;
- topics and classifications;
- attachments;
- links;
- provenance;
- extensions.

Nothing important should be inferred only from a matching filename.

## Source And Derived Areas

Bundles should make it clear which resources are source material and which are derived.

For example:

```text
source/
  recording.m4a

derived/
  transcript.json
  transcript.md
  summary.md
  embeddings.json
```

The exact directory names are not final. The principle is that original material, human-readable forms, generated derivatives, and user edits should be distinguishable.

## Reprocessing

Bundles make reprocessing safer.

If the original source remains inside or associated with the bundle, a newer transcription model, speaker identifier, summariser, or link suggester can produce updated artefacts later.

Reprocessing must not silently destroy human corrections. If a transcript has been edited by a person, a new machine transcript should become a new version or proposal, with provenance preserved.

## Sync

Bundles should be designed with ordinary sync tools in mind.

Users may store Onbii objects in iCloud Drive, Dropbox, OneDrive, Nextcloud, Syncthing, Git, a NAS, or a local folder. The bundle model should reduce accidental separation of related resources, but sync conflict handling is not yet specified.

## Open Questions

The following details remain open:

- whether `.onbii` is always a directory package, a ZIP-based package, or may support both;
- the exact manifest format;
- required internal directory names;
- how platform-specific package metadata should work;
- how large media files should be handled by sync tools;
- how conflicts and concurrent edits should be represented.
