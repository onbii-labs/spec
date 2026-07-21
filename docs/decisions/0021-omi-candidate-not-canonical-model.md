# 0021: Omi Is A Candidate Source, Not The Canonical Model

Status: Accepted

Date: 2026-07-21

## Context

Omi appears to solve some capture and API problems that overlap with Onbii's goals. It may provide useful integration patterns or source material.

However, its backend-oriented model does not match Onbii's desired user-owned, local-first knowledge store. Even open-source backend infrastructure can still be too SaaS-like or operationally heavy for ordinary users.

## Decision

Omi should be treated as a possible source or adapter candidate, not as the canonical Onbii model.

Onbii should not recreate Omi's backend approach. It may ingest from Omi if that proves useful.

## Consequences

- Omi can remain an adapter research candidate.
- Onbii's core model should remain user-owned and local-first.
- The roadmap should avoid implying Omi is the obvious first target.
- Any Omi work should focus on bringing material into Onbii objects.
