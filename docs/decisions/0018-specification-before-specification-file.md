# 0018: Avoid `SPECIFICATION.md` Until The Format Is Clearer

Status: Accepted

Date: 2026-07-21

## Context

The project needs to describe its vision, principles, roadmap, object abstraction, bundle model, linking, and provenance before pretending the specification is stable.

A premature `SPECIFICATION.md` risks sounding more definitive than the format actually is.

## Decision

Do not write a central `SPECIFICATION.md` yet.

Start with focused documents that explain the concepts and constraints. Create a formal specification document only once the object model, bundle format, linking, and provenance model are clearer.

## Consequences

- Early docs can remain explanatory and exploratory where needed.
- The project avoids over-specifying before examples exist.
- The first formal specification can later consolidate decisions already tested in focused docs and examples.
- Contributors should look to the current docs and decisions for direction until a formal specification exists.
