# Versioning

## Specification Versioning

The Onbii Specification follows **Semantic Versioning 2.0.0**.

Version numbers take the form:

```
MAJOR.MINOR.PATCH
```

For example:

```
1.0.0
```

## Major Releases

A major version indicates incompatible changes to the specification.

Examples include:

- breaking changes to object structures;
- removal of previously supported features;
- incompatible changes to metadata;
- changes requiring existing implementations to modify behaviour.

Major releases should be rare.

## Minor Releases

A minor version introduces new functionality while remaining backwards compatible.

Examples include:

- new optional metadata;
- additional object types;
- new recommendations;
- clarification of existing behaviour;
- new extension points.

Existing compliant implementations should continue to operate correctly.

## Patch Releases

Patch releases do not change the behaviour of the specification.

Examples include:

- correcting errors;
- improving wording;
- fixing examples;
- correcting diagrams;
- editorial improvements.

Implementations should not require changes following a patch release.

## Backwards Compatibility

Backwards compatibility is a primary design goal of the Onbii Specification.

Where possible:

- existing knowledge objects should remain valid;
- existing implementations should continue to function;
- new functionality should be additive rather than disruptive.

Breaking changes should only be introduced when there is no practical alternative.

## Experimental Features

Experimental features may be documented before they become part of the specification.

Such features will be clearly identified as experimental and should not be relied upon for production implementations.

Experimental features may change or be removed without notice.

## Deprecation

Features should normally be deprecated before removal.

Where practical, the specification will:

1. mark a feature as deprecated;
2. explain the preferred alternative;
3. retain compatibility for at least one major version before removal.

## Extensions

The specification is designed to be extensible.

Implementations may introduce vendor-specific extensions provided they:

- do not alter the meaning of standard fields;
- do not reduce interoperability;
- clearly distinguish extension data from standard specification elements.

## Version History

A changelog is maintained in `CHANGELOG.md`.
