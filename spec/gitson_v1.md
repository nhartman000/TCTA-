# GITSON Specification — Historical / Auxiliary Profile

> **Current status (August 2026):** this document is retained as historical development material. GITSon is auxiliary to the current TCTA/MG8 architecture and is **not required by the canonical MG8 core file family**. Current gate, state, orchestration, unit, package, and trace roles are assigned to `.g8son`, `.gst`, `.ork`, `.mg8`, `.mg8pk`, and `.qson` respectively. See https://github.com/nhartman000/gitson- for the current GITSon status boundary.

> The material below preserves the earlier Version 1.0 design direction for provenance. Statements about migration/conformance should be read in that historical context rather than as current canonical requirements.

## Version 1.0 — Historical Design

### Overview
The GITSON format was designed as an optimized JSON-oriented specification for integrating structured content with GitHub and other version-control systems. The earlier design explored MMOL integration, file-size management strategies, relationships to g8son/gst/mg8 artifacts, lexical footnote standards, compact mode, and validation requirements.

### MMOL Integration
- Explore integration with MMOL (Multi-Model Object Linking) for linking multiple database models within the structured representation.

### File Size Management Strategy
- Control nested depth and unnecessary redundancy where repository/tooling limits require bounded transport.
- Use references where an implementation profile supports them.

Platform-specific file-size limits are not permanent semantic properties of GITSon; adapters should track those independently.

### Historical Conformance Direction
Earlier work proposed relationships to:

- **g8son**
- **gst**
- **mg8**

Those relationships predate the current dedicated canonical specifications. A modern implementation must validate each artifact against its current format authority rather than assuming GITSon supersedes or wraps it.

### Lexical Footnote Standards
The historical design explored lexical footnotes for contextual metadata without expanding the main structured payload.

### Compact Mode
The historical design explored compact transmission/storage representations that reduce redundant fields and whitespace.

### Validation Requirements
The historical design called for explicit validation rules and schemas for conforming GITSon artifacts.

## Current Relationship to TCTA

TCTA does not require GITSon to define its State Representation, trajectory, prefix invariant, OGSI, HDRP, or CIIU formalism.

Existing `.gitson` examples in this repository are retained as implementation/provenance artifacts. Their presence should not be interpreted as making GITSon part of the TCTA mathematical core.

## Preservation Rule

Do not delete or mechanically rename historical GITSon artifacts merely to match the newer file family. Preserve them where needed for provenance, and migrate only after determining the semantic role of each artifact.
