# Lore Search Fixture

## Status

Non-canonical test fixture for Skill rehearsal only.

## Purpose

This fixture tests whether `lore-search` can:

- search the repo for a linked concept cluster instead of one isolated term
- distinguish canon, state, and prep for Arven, the true Emon return, and branch memory
- return a cited answer useful for Session 6 prep
- avoid overloading the search with unrelated campaign context

## Prompt

Build a short lore briefing for the GM before Session 6 answering:

- What is firmly established about Arven?
- What is firmly established about the return to the true Emon?
- Who remembers the collapsed branch?
- What current prep assumption matters most for keeping Session 6 grounded?

## Expected Boundary

- read-only rehearsal output only
- all claims should point back to searched files
- prep assumptions must stay clearly separate from canon and state
