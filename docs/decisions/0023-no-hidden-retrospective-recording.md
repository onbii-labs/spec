# 0023: No Hidden Retrospective Recording Assumption

Status: Accepted

Date: 2026-07-21

## Context

An early idea compared capture to Apple Fitness detecting a walk and asking whether to record from the start. For audio, that kind of hidden retrospective capture is not generally feasible or appropriate on Apple platforms.

Recording requires user awareness and permission. The project should not build its roadmap on invisible ambient audio buffers.

## Decision

Onbii should not assume hidden retrospective recording.

The useful "magic" should be in suggestions, explicit capture modes, and low-friction workflows, not in secretly recording before the user has chosen to capture.

## Consequences

- Capture adapters should respect platform permission models and consent expectations.
- Roadmap language should avoid promising ambient retrospective recording.
- Contextual detection may suggest capture, but actual audio capture should be explicit.
- Privacy and trust are part of the capture design, not afterthoughts.
