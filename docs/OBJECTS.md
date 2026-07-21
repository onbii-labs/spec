# Objects

Onbii is built around knowledge objects.

A knowledge object is a self-contained unit of knowledge with identity, source material, human-readable representations, machine-readable metadata, derived artefacts, provenance, and links to other objects.

The object is the thing the user means to keep.

## Why Objects

People do not usually think in sidecar files.

They think:

- "I had a meeting."
- "I recorded a voice memo."
- "I imported a podcast episode."
- "I saved a document."
- "I took a photo."
- "I spoke to this person."

Each of those may involve several files and many derived outputs, but conceptually it is one thing. Onbii should preserve that shape.

## Not Just A Markdown File

Markdown is important because it is human-readable, durable, and widely understood. It is a strong representation for transcripts, notes, summaries, and narratives.

But Markdown is not the whole object.

A recorded conversation may contain:

- original audio;
- a transcript;
- a human-corrected transcript;
- speaker attribution;
- a summary;
- action items;
- extracted entities;
- topics;
- classifications;
- attachments;
- source metadata;
- processing metadata;
- links to people, organisations, projects, and other conversations.

The Markdown view is one representation of the object. It should not be forced to carry every resource, timestamp, confidence score, provenance event, or binary attachment inline.

## Object Identity

Every knowledge object should have a stable identity.

That identity should remain stable when the user changes the title, moves the object, syncs it to another device, or views it through a different application.

Filenames and paths are useful for humans. They should not be the primary identity of the object.

## Object Contents

The exact manifest schema is not defined yet, but an Onbii knowledge object is expected to describe at least:

- identity;
- object type;
- title or display name;
- creation time;
- source material;
- human-readable representations;
- derived artefacts;
- human-set topics or classifications;
- provenance;
- links;
- optional extensions.

For example, a recorded conversation object may contain:

```text
Meeting with Jean-Paul.onbii/
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

This is illustrative, not yet a normative file layout.

## Source Material

Source material is the evidence or input from which other representations are created.

For a conversation, the source may be original audio. For a podcast, it may be the downloaded episode. For a document, it may be the imported file. For a photograph, it may be the original image.

Source material should be preserved wherever practical because it allows future tools to reinterpret the object.

## Human-Readable Representations

Objects should provide human-readable representations where practical.

For a recorded conversation, this may be a transcript and a readable note. For an imported document, it may be extracted text or a Markdown summary. For a photo, it may be a caption, OCR text, or description.

Human-readable representations make the object useful even when no AI model, database, or special application is available.

## Derived Artefacts

Derived artefacts are outputs generated from the source material or from other representations.

Examples include:

- transcripts;
- diarisation;
- speaker identification;
- summaries;
- action items;
- entities;
- topics;
- classifications;
- embeddings;
- suggested links;
- search indexes.

Derived artefacts should be traceable to their inputs and generators. They may be regenerated as models and tools improve.

## Topics And Classification

Topics and classifications help users and tools organise knowledge.

They may be created in different ways:

- set directly by a person;
- suggested by a model and later accepted or rejected;
- derived automatically during processing;
- imported from a source system.

Those cases should remain distinguishable. A human-set topic is not the same as a machine-suggested topic. A classification imported from another product is not the same as one generated locally.

The specification should allow topics and classifications without requiring a fixed taxonomy too early. Early examples should focus on representing where a topic came from and whether it has been reviewed, rather than defining every possible topic type.

## Human Edits

Human edits are part of the object history.

If a person corrects a transcript, changes a speaker attribution, edits a summary, or adds context, that should be preserved as a human contribution. It should not be indistinguishable from machine-generated output.

Reprocessing should preserve human edits and create new versions or proposals rather than silently overwriting them.

## Object Types

The first object type has not been finalised.

Recorded conversation is the strongest early candidate because it exercises many parts of the model:

- source audio;
- transcript;
- speaker information;
- human corrections;
- topics and classifications;
- summary;
- links;
- provenance;
- reprocessing;
- bundle storage;
- application views.

Other possible object types include voice memo, podcast episode, document, photo, email, person, company, task, receipt, and case material. These should not all be specified at once.

## Applications And Views

Different applications may show the same object differently.

Obsidian may show a Markdown projection. A desktop app may show the full bundle. Quick Look may show a preview. A search tool may index text and metadata. An AI assistant may use the transcript and links as context.

These are views over the object. They are not the object itself.
