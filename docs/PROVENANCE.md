# Provenance

Provenance describes where knowledge came from, how it was transformed, and which parts were created or changed by people or machines.

For Onbii, provenance is not an optional audit feature. It is part of what makes personal knowledge durable and trustworthy.

## Why Provenance Matters

AI systems can transcribe, summarise, classify, link, and reinterpret knowledge. Those outputs may be useful, but they are not the same as the source.

Onbii should preserve the difference between:

- what was originally captured or imported;
- what a machine derived from it;
- what a human corrected, approved, or added;
- what a human classified or tagged;
- what later tools regenerated or superseded.

Without that distinction, a user's archive becomes a pile of conclusions with no reliable way to understand where they came from.

## Source Material

Source material is the original input for a knowledge object.

Examples:

- the original audio of a conversation;
- an imported podcast episode;
- a voice memo;
- a photograph;
- a PDF;
- an email export;
- a document;
- a file from an investigation or disclosure.

Source material should be preserved wherever practical. It is the basis for future interpretation.

For a recorded conversation, the original audio is the source. A transcript is derived from it.

## Human-Readable Derived Forms

Some derived artefacts are intended for people.

For a conversation, the transcript is a human-readable derived form. It may become the practical basis for summaries, links, search, and later processing, but it should not be confused with the original audio.

A transcript may also be corrected by a human. That corrected transcript is no longer merely machine output; it is a human-edited artefact with its own provenance.

## Machine-Derived Artefacts

Machine-derived artefacts may include:

- raw transcripts;
- diarisation;
- speaker identification;
- summaries;
- action items;
- entities;
- topics;
- classifications;
- embeddings;
- suggested links;
- search indexes;
- graph projections.

These artefacts should record:

- the input they were generated from;
- the tool, model, or process that generated them;
- when they were generated;
- relevant configuration or version information where available;
- whether they have been superseded;
- whether a human has reviewed or edited them.

## Human Edits

Human edits must be visible in the object's history.

Examples include:

- correcting a misheard word in a transcript;
- assigning the right speaker to a passage;
- changing a generated title;
- editing a summary;
- adding or removing a topic;
- changing a classification;
- adding context that was not present in the source;
- approving or rejecting a suggested link.

These edits are valuable. They should not be erased by later reprocessing.

## Reprocessing

Reprocessing is expected.

Speech models will improve. Speaker identification may improve. Better summarisation and linking tools may appear. An Onbii object should be able to gain better derived artefacts over time because its source material and provenance remain available.

Reprocessing should create a new version, revision, or proposed update when it would affect human-edited content. It should not silently overwrite corrections or approved material.

## Layered Canonicality

The word "canonical" depends on the layer.

For a conversation:

- the original audio is the source;
- the transcript is a human-readable derived form;
- a corrected transcript may be the preferred human-readable working form;
- summaries, actions, links, embeddings, and graph projections are further derivatives;
- topics and classifications may be human-set, imported, suggested, or derived;
- the knowledge object and manifest bind these resources together.

The specification should avoid pretending that one file is canonical for every purpose.

## Provenance Events

The exact schema is not defined yet, but provenance should be expressible as events.

Examples:

```text
captured
imported
transcribed
speaker-attributed
summarised
topic-suggested
topic-set-by-human
classified
linked
edited-by-human
reviewed
reprocessed
superseded
exported
```

Each event should identify what changed, what caused the change, and which resource or version it affects.

## Privacy And Trust

Personal knowledge often contains sensitive material.

Provenance should help users understand whether a resource was processed locally, sent to an external AI provider, imported from a vendor system, or changed by another person. If an implementation uses cloud processing, external APIs, or shared workspaces, that should be visible in provenance where it affects the object.

## Derived Indexes

Indexes and databases are useful but should be rebuildable.

Graph databases, vector stores, search indexes, entity caches, and timelines should not become the only place where provenance lives. They may project information from objects, but the durable provenance should remain with or alongside the knowledge objects themselves.
