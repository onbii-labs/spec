# Decisions

This directory records important Onbii design decisions.

The goal is not to create heavy process. The goal is to preserve the reasoning behind choices that future contributors are likely to question.

Decision records should be used when a decision:

- affects the specification or long-term architecture;
- has meaningful alternatives;
- explains why Onbii does something unusual;
- would be painful to rediscover from old conversations, issues, or pull requests.

Smaller working decisions can remain in the relevant document until they become important enough to record separately.

## Index

| ID | Decision | Status |
| --- | --- | --- |
| [0001](0001-local-first.md) | Local-first knowledge ownership | Accepted |
| [0002](0002-knowledge-objects.md) | Knowledge objects as the primary abstraction | Accepted |
| [0003](0003-bundles-over-loose-sidecars.md) | Bundles over loose sidecar files | Accepted |
| [0004](0004-stable-identifiers.md) | Stable identifiers over filenames | Accepted |
| [0005](0005-not-ai-meeting-notes.md) | Onbii is not an AI meeting-notes product | Accepted |
| [0006](0006-capture-certainty-before-intelligence.md) | Capture certainty before intelligence | Accepted |
| [0007](0007-applications-are-views.md) | Applications are views | Accepted |
| [0008](0008-preserve-original-sources.md) | Preserve original sources | Accepted |
| [0009](0009-derived-data-is-not-truth.md) | Derived data is not truth | Accepted |
| [0010](0010-human-edits-are-protected.md) | Human edits are protected | Accepted |
| [0011](0011-bring-your-own-components.md) | Bring your own components | Accepted |
| [0012](0012-capture-source-pluralism.md) | Capture and source pluralism | Accepted |
| [0013](0013-source-vs-capture-adapters.md) | Source adapters and capture adapters are separate concepts | Accepted |
| [0014](0014-manual-plaud-export-not-foundation.md) | Manual Plaud export is not the foundation | Accepted |
| [0015](0015-no-generic-onbii-repository.md) | No generic `onbii` repository yet | Accepted |
| [0016](0016-documentation-in-spec.md) | Documentation lives in `spec` for now | Accepted |
| [0017](0017-avoid-github-wiki.md) | Avoid GitHub Wiki initially | Accepted |
| [0018](0018-specification-before-specification-file.md) | Avoid `SPECIFICATION.md` until the format is clearer | Accepted |
| [0019](0019-spec-docs-license.md) | Specification and documentation use CC BY 4.0 | Accepted |
| [0020](0020-mobile-matters-not-day-one.md) | Mobile matters, but not necessarily day one | Accepted |
| [0021](0021-omi-candidate-not-canonical-model.md) | Omi is a candidate source, not the canonical model | Accepted |
| [0022](0022-no-user-facing-graph-database.md) | No user-facing graph database requirement | Accepted |
| [0023](0023-no-hidden-retrospective-recording.md) | No hidden retrospective recording assumption | Accepted |
| [0024](0024-first-producer-workflow-open.md) | First producer workflow remains open | Open |
| [0025](0025-onbii-package-format-open.md) | Exact `.onbii` package format remains open | Open |
| [0026](0026-identifier-scheme-open.md) | Identifier scheme remains open | Open |
| [0027](0027-future-code-license-open.md) | Future code license remains open | Open |
| [0028](0028-onbii-name.md) | Project name is Onbii | Accepted |
| [0029](0029-compact-audio-originals.md) | Captured audio originals are compact, not lossless | Accepted |

## Status Values

- **Accepted**: the current project direction.
- **Tentative**: likely direction, but still open to revision.
- **Superseded**: replaced by a later decision.
- **Rejected**: considered and explicitly not chosen.

## Format

Decision records should usually include:

- status;
- date;
- context;
- decision;
- consequences.

They should stay short enough to read quickly.
