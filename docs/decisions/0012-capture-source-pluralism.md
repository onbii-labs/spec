# 0012: Capture And Source Pluralism

Status: Accepted

Date: 2026-07-21

## Context

The conversation considered many possible sources: Plaud, Omi, Apple Voice Memos, desktop call capture, phone calls, podcasts, YouTube, file drops, wearables, and future devices.

Different people will prefer different capture methods. A good device today may be replaced tomorrow.

## Decision

Onbii should support capture and source pluralism.

The recorder, wearable, app, import path, or media source should be treated as an edge component that can feed knowledge objects, not as the centre of the system.

## Consequences

- The specification should support source metadata without binding the model to one device.
- Adapter work should focus on normalising sources into Onbii objects.
- The roadmap should keep source candidates open until the first producer workflow is chosen.
- New devices or services can become additional sources without changing the core object model.
