# 0011: Bring Your Own Components

Status: Accepted

Date: 2026-07-21

## Context

People use different recorders, storage providers, sync tools, AI services, devices, and applications. Capture hardware, speech models, and AI providers are also changing quickly.

Onbii should not depend on one preferred vendor or one complete product stack.

## Decision

Onbii should allow people to bring their own recorder, storage, sync, AI provider, and client applications.

The specification should define boundaries that let those components interoperate over user-owned knowledge objects.

## Consequences

- Onbii should be capture-agnostic, AI-agnostic, storage-agnostic, and application-agnostic where practical.
- Implementations may combine several roles for convenience, but the conceptual boundaries should remain clear.
- Vendor-specific integrations should not define the core model.
- Documentation should avoid presenting any one recorder, AI provider, database, or sync service as required.
