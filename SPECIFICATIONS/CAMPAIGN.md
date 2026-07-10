# Purpose

Campaign defines the continuity boundary for all campaign knowledge. It holds campaign identity, system context, and operating status.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign identity
- game system
- campaign status
- reference context boundary

# Required Fields

- `campaign_name`
- `game_system`
- `campaign_status`

# Optional Fields

- `subtitle`
- `start_date`
- `end_date`
- `reference_context_refs`

# Constraints

- `campaign_status` is one of `planned`, `active`, `paused`, `completed`, or `archived`.
- Campaign records do not contain session history, events, or current world state.
- `reference_context_refs` point to non-canonical reference material only.
- All other campaign records belong to exactly one Campaign.

# References

- Source Record
- Session
- Working Record
- Event
- Entity
- Relationship
- Derived State
