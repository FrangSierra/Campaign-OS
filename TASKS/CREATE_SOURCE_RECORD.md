# Create Source Record

## Purpose

Convert raw session input into one or more Source Records while preserving original evidence.

## Inputs

- `campaign_ref`
- raw input as pasted content or stored source file
- `source_kind`

## Outputs

- Source Record files

## Dependencies

- [SOURCE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/SOURCE_RECORD.md)

## Files Read

- pasted raw input or raw files under `SOURCE/`

## Files Written

- Source Record files in the matching source directory

## Approval

- none

## Constraints

- evidence remains recoverable
- provenance is explicit
- no canon is asserted

## Failure

- missing input
- unknown `source_kind`
- unrecoverable evidence
