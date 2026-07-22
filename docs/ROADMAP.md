# Roadmap

This roadmap is organised around **when Onbii becomes useful**, not around when every technical concept is complete.

The central question is:

> When would someone actually want to use this?

Onbii should move from confidence, to personal usefulness, to richer recall, to broader capture, to an open ecosystem others can build on.

One design approach runs through every milestone:

> Onbii should not need a full Onbii app before it becomes useful.

The early format should be object-first, not loose-file-first. A recording, meeting, memo, or other captured item should behave like one manageable knowledge object, while still containing human-readable material that ordinary tools can inspect. Markdown remains a first-class view of the object, but it should not be forced to carry everything.

Small helpers are welcome early if they make that object easier to inspect: a basic Obsidian reader, a Finder or Quick Look preview, a tiny viewer, or another lightweight surface. Those helpers should reveal the object rather than become the system of record.

## Milestone 1: I Am Not Losing This

The first useful version of Onbii should give a person confidence that an important recording, memo, or conversation has been captured into something they own.

This is the first wedge: **capture certainty before intelligence**.

See also [Milestone 1 Breakdown](MILESTONE_1_BREAKDOWN.md) for the Apple-first capture-certainty breakdown.

A person should be able to say:

> "That conversation is in Onbii. I can come back to it later."

What must be true:

- a real recording can be brought into Onbii;
- the original recording is preserved;
- a basic transcript can be created, ideally using on-device capabilities where available;
- rough speaker turns can show who said what, even if speakers start as `Speaker 1` and `Speaker 2`;
- the result lives somewhere the user controls;
- the result behaves as one manageable knowledge object rather than a loose pile of related files;
- the user can inspect the object in an ordinary folder or package;
- the object contains a basic human-readable Markdown facet, such as a transcript or content view;
- a small reader or preview can be introduced if it helps people open the object without turning Onbii into a full application;
- basic information such as title, date, source, and people can be recorded;
- the object is not dependent on a single vendor account or app.

This milestone should not yet require templated notes, external AI provider choices, rich summaries, or advanced classification. The point is to make the first format usable enough to inspect and trust.

Early examples may use a controlled recording, a sample recording, Apple Voice Memos, a local desktop recording, or another practical source. Plaud exports can be used as examples or fallback material, but manual Plaud export is not the foundation of the desired experience.

User value:

> "The recording is safe, I can already see who said what, and it is not trapped in someone else's app."

## Milestone 2: I Can Use This After A Real Meeting

The next step is personal usefulness.

Onbii should be good enough for selected real meetings, calls, memos, or conversations. The workflow may still have rough edges, but the result should be worth returning to.

A person should be able to say:

> "I can put this meeting or memo into Onbii and actually use it later."

What must be true:

- the recording has a readable transcript or note;
- the user can correct names, speakers, titles, and mistakes;
- human edits are preserved rather than overwritten;
- a summary or outline can be attached when useful;
- topics and classifications can be added by the user or suggested by the system;
- the result can be browsed without needing to understand the internal format;
- tools such as Obsidian, Finder, VS Code, or plain text editors can expose the human-readable part of the object, even if they do not understand every internal resource yet;
- early plugins or previews can focus on reading and displaying Onbii objects before attempting richer graph, recall, or editing behaviour.

This milestone is less about perfect automation and more about proving that the archive is useful enough to keep feeding.

User value:

> "This is already better than a recording sitting in an app, because I can read it, fix it, find it, and build on it."

## Milestone 3: I Can See What Connects

Once there are multiple useful objects, Onbii should start showing the value beyond storage.

This is where Onbii becomes more than a personal folder of notes.

A person should be able to ask:

- What did I discuss with John?
- Who else was interested in this?
- Did Peter or Paul mention something related?
- Which earlier conversations led to this decision?
- What did I promise to follow up on?
- Has this topic changed since we last talked about it?

What must be true:

- objects can link to people, projects, topics, decisions, and follow-ups;
- links can be human-set or suggested;
- topics and classifications can be human-set or suggested;
- related objects can be surfaced;
- search works across the local archive;
- AI-assisted recall can answer questions from the user's own knowledge.

User value:

> "I can see what I discussed, who else cared, what connects, and what changed."

## Milestone 4: Getting Things Into Onbii Becomes Easier

After the first useful loop works, capture should become less annoying.

The project should then reduce the friction of getting real material into Onbii from the places people already use.

Candidate paths:

- desktop call capture for Zoom, Teams, Nextcloud Talk, or similar;
- Apple Voice Memos import;
- local file or folder watching;
- Plaud import research;
- Omi research, if it proves practical enough;
- podcast or media ingestion;
- mobile capture or mobile-to-desktop sync.

What must be true:

- at least one repeatable source path exists;
- imported material carries useful source information;
- the user does not have to manually file and rename everything;
- recordings and derived notes still end up in the user's own archive;
- mobile is treated as strategically important, even if the first learning happens in a more controlled desktop workflow.

User value:

> "Using Onbii is becoming part of how I already capture things, rather than another chore."

## Milestone 5: I Can Rely On It

Onbii becomes personally trustworthy when it can support repeated use over time.

At this point, the archive is no longer just an experiment. It should begin to feel like contacts, calendar, or email: something a person can return to and depend on.

What must be true:

- objects remain understandable over time;
- corrections and reprocessing history are preserved;
- source material remains available where appropriate;
- search and recall continue to work as the archive grows;
- better models or tools can improve derived outputs without destroying human work;
- the archive can be backed up, moved, or opened outside a single app.

User value:

> "I trust this enough to keep using it."

## Milestone 6: Others Can Understand And Build With It

Once the first useful loop has been proven, the public specification becomes more valuable.

The specification should explain the model clearly enough that other people can critique it, implement against it, or build compatible tools.

What must be true:

- the object model is described with worked examples;
- the bundle/package format is described with worked examples;
- provenance, human edits, linking, topics, and classifications are described;
- unresolved questions are clearly marked;
- contributor guidance exists for proposals and experiments;
- examples are understandable without reading the original design-history recovery.

User value:

> "I can understand what Onbii is, try it, and see how I might build something compatible."

## Milestone 7: One Memory, Many Tools

The longer-term goal is for Onbii to become a shared foundation for personal knowledge tools.

Onbii should not require everyone to use the same app, recorder, storage provider, AI model, or browsing surface.

Possible directions:

- richer Obsidian behaviour for links, graph views, editing, and object navigation;
- a mobile capture and browsing app;
- more polished desktop preview or Quick Look experiences;
- command-line tools;
- richer local search and AI recall;
- source adapters for recorders, voice memos, calls, podcasts, and media;
- collaboration or shared workspaces where appropriate.

User value:

> "My knowledge can move with me, and different tools can work with the same memory."
