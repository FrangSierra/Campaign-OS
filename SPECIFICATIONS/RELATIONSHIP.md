# Purpose

Relationship defines a stable semantic link between Entities. It is reserved for persistent or independently queryable connections, not one-off interactions.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign scope
- subject entity
- predicate
- object entity
- relationship status
- optional event-backed timing

# Required Fields

- `campaign_ref`
- `subject_ref`
- `predicate`
- `object_ref`
- `relationship_status`

# Optional Fields

- `start_event_ref`
- `end_event_ref`
- `scope_notes`
- `strength`
- `secrecy`

# Constraints

- `campaign_ref` resolves to one Campaign.
- `subject_ref` and `object_ref` resolve to Entities in the same Campaign.
- `predicate` is not empty.
- `relationship_status` is one of `proposed`, `active`, `inactive`, `ended`, or `archived`.
- `start_event_ref` and `end_event_ref`, if present, resolve to Events.
- Relationship records are used only for stable or independently queryable links.

# References

- Campaign
- Entity
- Event
- Working Record
- Derived State
