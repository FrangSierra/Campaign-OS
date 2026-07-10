# Campaign Status

## Purpose

Track operational campaign state for the Echoes of Tal Dorei campaign. This document is operational, not canonical.

## Fields

- `campaign_os_version`: `1.0.0-mvp`
- `campaign_version`: `1.0.0`
- `latest_imported_session`: `session-005-the-rune-breaks`
- `latest_canonical_event`: `event-session-005-timeline-stabilized-and-agency-recruitment`
- `latest_derived_state_update`: `2026-07-10T21:15:00+02:00`
- `pending_working_records`: `0`
- `pending_approvals`: `0`
- `open_mysteries`: `4`
- `known_contradictions`: `0`
- `health_status`: `active`

## Constraints

- Values summarize operational state only.
- Canonical facts remain in `CANON/`.
- Derived summaries remain in `STATE/`.
- Working counts and approval counts may be updated as sessions are processed.
- `latest_imported_session` may be ahead of `latest_canonical_event` while approvals are pending.

## Notes

Initialize empty values until the first real session is imported.
