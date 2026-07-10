# Campaign Status

## Purpose

Track operational campaign state for the Echoes of Tal Dorei campaign. This document is operational, not canonical.

## Fields

- `campaign_os_version`: `1.0.0-mvp`
- `campaign_version`: `1.0.0`
- `latest_imported_session`:
- `latest_canonical_event`:
- `latest_derived_state_update`:
- `pending_working_records`: `0`
- `pending_approvals`: `0`
- `open_mysteries`: `0`
- `known_contradictions`: `0`
- `health_status`: `initialized`

## Constraints

- Values summarize operational state only.
- Canonical facts remain in `CANON/`.
- Derived summaries remain in `STATE/`.
- Working counts and approval counts may be updated as sessions are processed.

## Notes

Initialize empty values until the first real session is imported.
