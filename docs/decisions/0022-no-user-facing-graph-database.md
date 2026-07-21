# 0022: No User-Facing Graph Database Requirement

Status: Accepted

Date: 2026-07-21

## Context

Graph databases, vector stores, search indexes, entity stores, and other machine-optimised systems may be useful for querying and connecting Onbii knowledge.

However, ordinary users should not have to understand graph theory, run Neo4j, operate vector infrastructure, or upload their knowledge into a database just to make the archive useful.

## Decision

Onbii should not require a user-facing graph database.

Graphs, vectors, indexes, and caches may exist as derived projections over knowledge objects. They should not become the only place where the user's knowledge or relationships live.

## Consequences

- The specification should not require Neo4j, Pinecone, or any specific graph/index technology.
- Machine-optimised structures should be rebuildable from objects and provenance where practical.
- Applications may render graph views without making the graph database the product.
- Documentation should treat these systems as implementation details, not user-facing prerequisites.
