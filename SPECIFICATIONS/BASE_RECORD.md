# Purpose

Base Record defines the shared contract for every persistent record in Campaign OS. It owns identity, schema versioning, lifecycle, timestamps, provenance, and shared extension fields.

# Inherits

None.

# Adds

- stable global identity
- explicit record classification
- schema version
- lifecycle state
- creation and update timestamps
- provenance
- optional metadata, links, and tags
- optional supersession chain

# Required Fields

- `id`
- `record_type`
- `schema_version`
- `lifecycle_state`
- `created_at`
- `updated_at`
- `provenance`

# Optional Fields

- `metadata`
- `links`
- `tags`
- `supersedes`
- `superseded_by`
- `notes`

# Constraints

- `id` is globally unique within the repository scope.
- `record_type` maps to one specification.
- `schema_version` is supported by the operating system.
- `lifecycle_state` is one of `draft`, `active`, `superseded`, `retired`, or `archived`.
- `updated_at` is not earlier than `created_at`.
- `provenance` is never empty.
- `links` resolve, are explicitly external, or are explicitly marked unresolved.
- `supersedes` and `superseded_by` do not contradict each other.
- Structured fields remain separable from descriptive content.

# References

- [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- [INVARIANTS.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/INVARIANTS.md)
- [STYLE_GUIDE.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/STYLE_GUIDE.md)
