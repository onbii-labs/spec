# 0013: Source Adapters And Capture Adapters Are Separate Concepts

Status: Accepted

Date: 2026-07-21

## Context

Early discussion used "capture" broadly for any way of getting audio or media into the system. That became too broad once the scope included podcasts, existing recordings, files, exports, webhooks, and live recording.

A live meeting detector and a podcast importer do not do the same job, even if both eventually produce material for an Onbii object.

## Decision

Onbii should distinguish source adapters from capture adapters.

A source adapter normalises an acquired artefact so it can become or contribute to an Onbii object.

A capture adapter handles live acquisition or detection, such as recording a call or suggesting capture during a meeting, and can pass the resulting artefact onward.

## Consequences

- Source adapters are the broader boundary.
- Capture adapters can be treated as live producer components.
- Adapter documentation should avoid making transcription, summarisation, or storage part of the adapter's core responsibility unless an implementation deliberately combines roles.
- The exact adapter interfaces remain to be specified.
