# Specification Style Guide

## Purpose

Specifications are interface contracts for Campaign OS. They define what a record or contract must contain, not how the system behaves at runtime.

## Audience

- maintainers
- template authors
- workflow and task authors
- reviewers validating repository consistency

## Writing Philosophy

- prefer contract over explanation
- prefer reference over repetition
- keep one responsibility per specification
- keep specifications scannable
- keep behavior in runtime documents, not specifications

## Required Structure

Every specification uses this structure in this order:

1. `# Purpose`
2. `# Inherits`
3. `# Adds`
4. `# Required Fields`
5. `# Optional Fields`
6. `# Constraints`
7. `# References`
8. `# Remarks` only when necessary

## Naming Conventions

- Use singular concept names: `Campaign`, `Source Record`, `Session`, `Event`, `Entity`, `Relationship`, `Working Record`, `Derived State`, `Base Record`.
- Use exact field names in backticks.
- Use status fields with explicit names such as `campaign_status`, `source_status`, `session_status`, `entity_status`, `relationship_status`, `working_status`, and `derived_status`.

## Inheritance Rules

- Base Record owns all shared persistent-record fields and shared validation philosophy.
- Derived specifications list only fields they introduce.
- Derived specifications do not restate inherited behavior.
- Non-record specifications use `None` in `Inherits`.

## Field Naming Conventions

- use snake_case
- use `_ref` for one reference
- use `_refs` for many references
- use `_status` for lifecycle or workflow sub-status
- use `_kind` for controlled record categories

## Constraint Style

- write constraints as short, testable statements
- avoid prose explanations inside constraints
- place shared constraints in Base Record
- place only record-specific constraints in derived specifications

## Reference Style

- reference related record types by exact concept name
- reference documents only when the document itself is the contract
- avoid repeating definitions from referenced records

## Expected Length

- target roughly 40 to 80 lines
- exceed that only when the contract would otherwise become ambiguous

## Contract Versus Documentation

Specifications define interfaces. Runtime documents define behavior. ADRs explain decisions. Skills implement behavior. Templates instantiate Specifications.
