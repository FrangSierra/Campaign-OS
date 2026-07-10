# Generate Processing Report

## Purpose

Write the durable report for one Process Session run.

## Inputs

- `campaign_ref`
- references to run artifacts
- approval outcome

## Outputs

- one Processing Report

## Dependencies

- run artifacts produced by the workflow

## Files Read

- current run artifacts

## Files Written

- one report in `REPORTS/`

## Approval

- none

## Constraints

- the report covers the full processing chain
- approval status is explicit
- pending work is explicit

## Failure

- omitted material step
- incorrect approval status
- missing traceability
