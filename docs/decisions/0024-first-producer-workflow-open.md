# 0024: First Producer Workflow Remains Open

Status: Open

Date: 2026-07-21

## Context

Onbii needs something that produces valid knowledge objects before parsers, validators, adapters, or viewers become meaningful.

Candidate first workflows include controlled desktop call capture, manually supplied recordings, Apple Voice Memos, Plaud exports for examples, Omi integration, or another source.

## Decision

No first producer workflow has been chosen yet.

The first producer should be selected based on which path best demonstrates early user value and teaches the project what the object model needs.

## Consequences

- The roadmap should describe learning goals and candidate paths rather than lock in one source.
- Adapter repositories should not be created around a guessed first source.
- Examples may use manually supplied recordings while the real producer decision remains open.
- This decision should be revisited before implementation work starts.
