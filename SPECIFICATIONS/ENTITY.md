# Purpose

Entity defines one stable tracked thing in the campaign. It preserves identity across events, aliases, and current-state changes.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign scope
- entity kind
- canonical primary name
- entity status
- optional aliases and current state

# Required Fields

- `campaign_ref`
- `entity_kind`
- `primary_name`
- `entity_status`

# Optional Fields

- `aliases`
- `current_state`
- `character_sheet_ref`
- `relationship_refs`
- `timeline_refs`
- `asset_refs`

# Constraints

- `campaign_ref` resolves to one Campaign.
- `entity_kind` is not empty.
- `primary_name` is not empty.
- `entity_status` is one of `known`, `active`, `inactive`, `retired`, or `archived`.
- `current_state`, if present, is supportable from approved Events, Relationships, or explicit approval.
- Aliases do not replace identity history.

# References

- Campaign
- Event
- Relationship
- Derived State
