# Implementation Architecture Outline

This document describes an early technical shape for Onbii implementations. It is not the formal specification.

The purpose is to keep early implementation work aligned with the roadmap, principles, and decisions while leaving feature-level implementation direction to concrete implementation repositories.

## Architecture Intent

Milestone 1 is titled **I Am Not Losing This**.

The first useful version of Onbii should give a person confidence that an important recording, memo, or conversation has been captured into something they own.

The early implementation architecture should therefore support:

- bringing a real recording into Onbii;
- preserving the original recording;
- creating a basic transcript;
- showing rough speaker turns;
- storing the result somewhere the user controls;
- making the result behave as one manageable knowledge object;
- allowing the user to inspect the object in an ordinary folder or package;
- including a basic human-readable Markdown facet;
- recording basic information such as title, date, location where available, source, and people;
- avoiding dependence on a single vendor account or app.

## First Proving Ground: Apple

The first implementation family should be Apple.

This does not make Onbii an Apple-only specification. Apple is the initial proving ground because the first users and testing devices are in the Apple ecosystem, and because Apple platforms offer practical capture surfaces across macOS, iPhone, and Apple Watch.

The Apple implementation should prove the Milestone 1 loop before broader platform work:

```text
capture surface
  -> preserved source recording
  -> Onbii knowledge object
  -> basic transcript
  -> rough speaker turns
  -> Markdown facet
  -> metadata, location where available, and provenance
  -> user-controlled archive
```

## Initial Capture Surfaces

Milestone 1 should include initial capture surfaces, not only an object writer.

### macOS

The first macOS surface should support starting and stopping capture around online meetings or desktop audio where practical.

It should also support importing an existing audio file for analysis. Import is important for testing, backfill, and controlled examples, but it should not replace the capture promise of the milestone.

### Apple Watch

Apple Watch should be treated as an important early capture surface.

The initial Watch experience can be simple: start recording, stop recording, preserve the audio, and transfer it onward so it can become an Onbii object. This supports moments where a person is away from the Mac, such as walking with someone, and wants to avoid losing the conversation.

### iPhone

The first iPhone surface should be simple and supportive:

- record directly;
- receive or coordinate Watch recordings;
- import or share audio into Onbii;
- help move captured material toward the user's Onbii archive.

The iPhone app does not need to become a full browsing or recall experience in Milestone 1.

## Core Boundaries

The Apple implementation may combine responsibilities for speed, but the concepts should remain distinct.

### Archive

The archive is a user-controlled location containing Onbii knowledge objects.

Examples:

- a local folder;
- an Obsidian vault;
- an iCloud Drive folder;
- a Git repository;
- another sync-backed folder chosen by the user.

The archive is the durable home of the user's knowledge. Applications, processors, and indexes are replaceable.

### Knowledge Object

A knowledge object is the durable unit the user means to keep.

For Milestone 1, the primary object type is likely a recorded conversation or voice memo because it exercises source preservation, transcription, speaker turns, Markdown views, metadata, and provenance.

### Bundle File Format

Milestone 1 should produce the first version of the `.onbii` bundle file format.

This should be a real bundle format, not a loose collection of sidecar files and not merely an illustrative directory used before a later bundle exists. The bundle should appear to the user as one manageable object while remaining inspectable through ordinary files inside, in line with the bundle model.

The first version can still be revised as the specification matures, but Milestone 1 should make the bundle concrete enough for captured recordings to be trusted, moved, copied, backed up, and inspected as Onbii objects.

### Capture Surface

A capture surface is a user-facing place where capture begins or is brought into Onbii.

For Milestone 1, the initial surfaces are expected to be macOS, Apple Watch, and iPhone in narrow forms.

### Source Adapter

A source adapter normalises an acquired artefact so it can enter Onbii.

For Milestone 1, this should handle audio captured or imported from the Apple surfaces and record enough source metadata to explain where it came from.

### Processing Pipeline

The processing pipeline creates derived artefacts from source material.

For Milestone 1, the pipeline can be minimal:

- transcribe the audio;
- produce rough speaker turns where possible;
- create a Markdown transcript or content view;
- record provenance for each derived artefact.

Advanced summaries, topic extraction, entity linking, embeddings, and recall can wait.

### Readers And Previews

Readers and previews help the user inspect captured objects.

Early useful readers may include:

- Finder or Quick Look preview;
- generated Markdown projection;
- a small local viewer;
- an Obsidian reader.

These help with inspection and trust. They should not become the durable home of the user's knowledge.

### Rebuildable Indexes

Search indexes, graph stores, vector stores, caches, and databases should be rebuildable from knowledge objects where practical.

Milestone 1 does not need a durable index unless it directly supports inspection or validation.

## Suggested Repository Shape

The first implementation repository should probably be:

```text
onbii-apple
```

Possible structure:

```text
onbii-apple/
  docs/
    spec/
    architecture/
    milestones/
  Packages/
    OnbiiCore/
    OnbiiArchive/
    OnbiiCapture/
    OnbiiTranscription/
  Apps/
    OnbiiMac/
    OnbiiIOS/
    OnbiiWatch/
  Extensions/
    QuickLook/
    ShareExtension/
  Tools/
    onbii-dev/
```

The `docs/spec/` directory should contain this specification repository as a submodule, subtree, or versioned copy. That keeps the product and specification context available to humans and AI agents working in the implementation repository.

Feature-level Apple direction should live in `onbii-apple/docs/`, not in this repository. The spec repository should define the shared constraints and product intent; the Apple repository should decide implementation details such as entitlements, audio capture APIs, transfer mechanisms, app targets, and release sequencing.

## Repository Approach

Repository naming and scope should follow [decision 0015](decisions/0015-no-generic-onbii-repository.md).

The `spec` repository remains the canonical home for the specification and project docs for now. Implementation repositories should be created only when their scope is clear, and the first implementation should be driven by the first useful producer workflow rather than by a placeholder repository name.

Given the chosen Apple-first proving ground, `onbii-apple` is a concrete implementation boundary. This does not replace or revise the accepted repository naming decision.

## Milestone 1 Technical Direction

Milestone 1 should answer the roadmap question in implementation form:

> Can a person capture an important recording, memo, or conversation into something they own, inspect it, and trust that they are not losing it?

One reasonable Apple-first path is:

1. Build a minimal macOS capture surface for start/stop recording around meetings or desktop audio where practical.
2. Add macOS import for existing audio files.
3. Create the shared Onbii object writer.
4. Preserve the original recording in or with the object.
5. Generate a basic transcript and Markdown facet.
6. Represent rough speaker turns where possible.
7. Record title, date, location where available, source, people where known, object identity, and provenance.
8. Store the object in a user-controlled archive.
9. Add a simple Apple Watch recording surface and transfer path.
10. Add a simple iPhone recording/import/receive surface.
11. Add enough inspection or preview support for the user to trust the captured object.

## Open Apple Implementation Questions

These questions are specific to the Apple proving ground. They can live here while `onbii-apple` does not yet exist, but should be answered and maintained in `onbii-apple/docs/` once that repository is created.

- Which macOS audio capture path is practical for the first meeting-oriented prototype?
- What should the start/stop capture surface feel like on macOS?
- How should pre-existing audio import work on macOS?
- Should the first transcript path use Apple on-device capabilities directly, and where should future third-party or server processing settings live?
- How should Apple Watch recordings transfer into the Onbii object flow?
- What should the simple iPhone record/import/receive flow include?
- Where should the user's first Onbii archive live by default on Apple platforms?
- What permissions, entitlements, and user-facing consent flows are required for capture, location, and transcription?
- What minimum manifest fields are required for the first `.onbii` bundle file format?
- How should human corrections be represented before full versioning is designed?
