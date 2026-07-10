# Purpose

Domain Model defines the minimum campaign knowledge model for the MVP. It fixes the accepted record types and the Truth Pipeline they follow.

# Inherits

None.

# Adds

- accepted record types: Campaign, Source Record, Session, Working Record, Event, Entity, Relationship, Derived State
- Truth Pipeline ordering
- separation between campaign knowledge and execution/runtime concepts

# Required Fields

None.

# Optional Fields

None.

# Constraints

- The Truth Pipeline is `Source Record -> Session -> Working Record (optional) -> Event -> Entity and Relationship updates -> Derived State`.
- Campaign knowledge begins with Source Records, not canon.
- Session records observation, not final world-history truth.
- Event records canonical world-history truth.
- Entity and Relationship updates are supportable from canonical Events.
- Derived State is never canonical.
- Commands, workflows, tasks, reports, and runtime helpers are not domain records.
- The model remains acyclic.

# References

- [BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)
- [CAMPAIGN.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/CAMPAIGN.md)
- [SOURCE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/SOURCE_RECORD.md)
- [SESSION.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/SESSION.md)
- [WORKING_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/WORKING_RECORD.md)
- [EVENT.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/EVENT.md)
- [ENTITY.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/ENTITY.md)
- [RELATIONSHIP.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/RELATIONSHIP.md)
- [DERIVED_STATE.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/DERIVED_STATE.md)
