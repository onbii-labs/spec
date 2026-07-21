# Linking

Onbii links knowledge objects to each other.

Links make it possible for a conversation, person, project, company, topic, document, photo, task, or imported audio source to become part of a wider body of knowledge without being copied into every place it is relevant.

## Why Links Matter

The value of preserved knowledge often appears later.

A meeting may become important because of a later discussion. A podcast may connect to a project months after it was imported. A person may be relevant to several conversations, companies, documents, and decisions. A transcript may contradict or support something captured elsewhere.

Onbii should preserve those relationships in a way that survives application changes.

## Stable Identity

Links should target stable object identities, not filenames or titles.

Human-readable names change. Files move. Folders are reorganised. Objects are synced between devices. A link should not break merely because a bundle was renamed from:

```text
Weekly Review.onbii
```

to:

```text
Meeting with Jean-Paul.onbii
```

The object's stable identifier should remain the same.

## Human Names Still Matter

Stable identifiers are for durability. Human-readable names are for usability.

Applications should be free to render links as readable titles, Obsidian-style wiki links, graph edges, timelines, search results, previews, or contextual suggestions.

The specification should not require users to think in opaque IDs.

## Objects As Link Targets

Links should be able to target first-class objects.

Possible object types include:

- conversation;
- voice memo;
- podcast episode;
- document;
- photo;
- person;
- organisation;
- project;
- topic;
- task;
- decision;
- receipt;
- case material.

This list is illustrative. It should not be treated as a complete taxonomy.

## Relationship Types

Some links are simple references. Others carry meaning.

Examples:

```text
mentions
participant
about
source-for
derived-from
contradicts
supports
supersedes
assigned-to
related-to
```

The exact relationship vocabulary is not defined yet. It should emerge carefully from real object examples rather than from abstract modelling.

## Topics And Classifications

Topics and classifications sit close to linking, but they are not exactly the same thing.

A topic may behave like a link target: a conversation can be about a topic, mention a topic, or become relevant to a topic later. A classification may describe how an object should be grouped, routed, reviewed, or displayed.

Both may be human-set or machine-derived. That distinction should be preserved. For example:

- a person tags a conversation as `BARP`;
- a model suggests `financial asset intelligence`;
- an imported system classifies a recording as `meeting`;
- a later review approves or rejects a suggested topic.

The specification should not require a complete ontology before the basic object model works. It should first preserve the topic or classification, its source, and its review status.

## Application Views

Different applications may project the same links differently.

Obsidian may show graph edges or Markdown links. A case view may show evidence chains. A CRM-like view may show people and interactions. A search interface may rank related material. An AI assistant may use links as context.

Those views should not own the relationships. They should interpret relationships stored in or derived from the Onbii objects.

## Suggested Links

AI and processing tools may suggest links.

Suggested links should be distinguishable from human-created or human-approved links. They should carry provenance, including the tool or model that suggested them and the input used.

A user or application may later approve, reject, edit, or supersede a suggested link.

## Links And Provenance

Some relationships are provenance relationships.

For example:

- a transcript is derived from an audio recording;
- a summary is derived from a transcript;
- an entity list is extracted from a transcript;
- a corrected transcript supersedes a raw transcript;
- a human-approved topic supersedes a machine-suggested topic;
- a new summary supersedes an older generated summary.

These relationships should be represented consistently with the provenance model.

## Obsidian Compatibility

Obsidian is an important potential view and editing environment, but Onbii links should not be limited to Obsidian's filename-based linking model.

An Obsidian plugin or projection may render Onbii links as familiar Markdown links where useful. Internally, Onbii should preserve stable object identity and relationship metadata.

## Open Questions

The following details remain open:

- the identifier scheme;
- the link syntax in manifests or companion files;
- whether relationship types are controlled, extensible, or both;
- how topics and classifications are represented;
- how human-set topics differ from suggested or derived topics;
- how links are represented in Markdown projections;
- how broken or missing targets are handled;
- how suggested links become approved links;
- how links behave across synced or shared archives.
