# Milestone 1 Breakdown: I Am Not Losing This

The first useful version of Onbii should give a person confidence that an important recording, memo, or conversation has been captured into something they own.

This milestone is the first wedge: **capture certainty before intelligence**.

## User Promise

A person should be able to say:

> "That conversation is in Onbii. I can come back to it later."

The implementation breakdown should preserve that promise. The captured item should be safe, readable, inspectable, and owned by the user.

## First Implementation Family

Apple should be the first implementation family for Milestone 1.

This is an initial proving ground, not a restriction on the Onbii specification. Apple is the right first family because the expected early users are in the Apple ecosystem and the available test devices include Mac, iPhone, and Apple Watch.

## Milestone 1 Surfaces

Milestone 1 should include initial capture surfaces across the Apple family.

### macOS Capture

The macOS surface should support starting and stopping capture around online meetings or desktop audio where practical.

It should help answer the milestone promise directly: the conversation happened on or near the Mac, and now it is in Onbii.

### macOS Import

The macOS app should also support importing an existing audio file for analysis.

Import is valuable for testing, backfill, controlled recordings, and sample material. It is part of the milestone, but it should not be treated as the whole capture experience.

### Apple Watch Capture

Apple Watch should be the second important capture surface.

The first Watch version can be simple: start recording, stop recording, preserve the audio, and transfer it onward so it can become an Onbii object. This supports moments such as walking with someone, where the user wants to keep a conversation without returning to the Mac first.

### iPhone Capture

The iPhone surface should be simple in Milestone 1.

It may:

- record directly;
- receive or coordinate Watch recordings;
- import or share audio into Onbii;
- help move captured material into the user's archive.

The iPhone app does not need full recall, browsing, or editing in this milestone.

## Shared Milestone Flow

Each capture surface should feed the same Onbii object flow:

```text
capture or import
  -> preserve original recording
  -> create one manageable knowledge object
  -> create basic transcript
  -> represent rough speaker turns
  -> create human-readable Markdown facet
  -> record title, date, location where available, source, people, and provenance
  -> store in user-controlled archive
  -> allow ordinary inspection or lightweight preview
```

## Workstreams

### Capture

Build the initial Apple capture surfaces:

- macOS start/stop capture;
- macOS audio import;
- Apple Watch start/stop recording and transfer;
- simple iPhone record/import/receive flow.

The first versions can be narrow. They should be real enough to test with actual recordings, memos, or conversations.

Capture should preserve available context from the moment of capture, including location where the device can provide it and the user has allowed it.

### Source Preservation

Preserve the original recording.

The user should not only receive a transcript, summary, or generated note. The original source material is part of the knowledge object or is clearly referenced if embedding is impractical.

### User-Controlled Archive

Store the result somewhere the user controls.

For the first Apple implementation, this may begin as a local folder or iCloud-accessible folder. The important requirement is that the object is not dependent on a single vendor account or app.

### Manageable Knowledge Object

The result should behave as one manageable knowledge object rather than a loose pile of related files.

Milestone 1 should produce the first version of the `.onbii` bundle file format.

That bundle should be the format used by the first capture surfaces, not a temporary directory used before Onbii has a bundle. It can still evolve, but the milestone should create real Onbii bundle objects that can be moved, copied, backed up, and inspected as one thing.

### Basic Transcript

Create a basic transcript.

On-device transcription should be the default where the device has suitable capabilities. Future settings may allow third-party functions, servers, or other processing providers, but Milestone 1 should not require advanced provider choice before the basic capture-certainty loop works.

### Rough Speaker Turns

Show rough speaker turns so the user can see who said what.

Speakers may start as `Speaker 1` and `Speaker 2`.

### Human-Readable Markdown Facet

Include a basic Markdown facet, such as a transcript or content view.

Markdown remains a first-class view of the object, but it should not be forced to carry everything.

### Basic Metadata

Record basic information such as:

- title;
- date;
- location where available;
- source;
- people, where known;
- object identity.

### Provenance

Record enough provenance to distinguish original source material from derived artefacts such as transcripts or speaker turns.

### Inspection

Allow the user to inspect the object in an ordinary folder or package.

A small reader or preview can be introduced if it helps people open the object without turning Onbii into a full application.

## What Milestone 1 Does Not Yet Require

The roadmap says this milestone should not yet require:

- templated notes;
- external AI provider choices;
- rich summaries;
- advanced classification.

It also does not need to solve every capture source, every meeting app, full recall, or polished long-term editing before the first capture-certainty loop is useful.

## Exit Criteria

Milestone 1 is complete when:

- a real recording can be brought into Onbii;
- the original recording is preserved;
- a basic transcript can be created, ideally using on-device capabilities where available;
- rough speaker turns can show who said what, even if speakers start as `Speaker 1` and `Speaker 2`;
- the result lives somewhere the user controls;
- the result behaves as one manageable knowledge object rather than a loose pile of related files;
- the user can inspect the object in an ordinary folder or package;
- the object contains a basic human-readable Markdown facet, such as a transcript or content view;
- a small reader or preview can be introduced if it helps people open the object without turning Onbii into a full application;
- basic information such as title, date, location where available, source, and people can be recorded;
- the object is not dependent on a single vendor account or app.

The milestone should leave the project with an Apple-first capture-certainty loop and a concrete basis for the `onbii-apple` implementation repository.

## Repository Placement

Feature-level Apple implementation direction should live in the Apple implementation repository, not in this spec repository.

Recommended shape:

```text
onbii-apple/
  docs/
    spec/
    architecture/
    milestones/
```

The `docs/spec/` directory should contain this spec repository as a submodule, subtree, or versioned copy so implementation work has the product context close at hand.
