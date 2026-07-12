---
name: process-session
description: Use when the user wants to process a played RPG session inside Campaign OS, turning notes, transcripts, PDFs, images, or pasted summaries into Source Records, a Session, optional Working Records, draft Events, a pending change set, and a processing report. Also use for safe rehearsal runs against fake roleplays, simulated chats, or test fixtures when the user wants to practice the workflow without touching canon.
---

# Process Session

This skill wraps the repository's existing Process Session command and workflow. It must preserve the Campaign OS Truth Pipeline and never replace the repo docs that define approval, provenance, or canon boundaries.

## Read First

Load only the minimum safe context, in this order:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `COMMANDS/PROCESS_SESSION.md`
4. `WORKFLOWS/PROCESS_SESSION.md`
5. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
6. The smallest relevant set of:
   - `SOURCE/`
   - touched `CANON/sessions/`, `CANON/events/`, `CANON/entities/`, `CANON/relationships/`
   - relevant `STATE/`
   - relevant `WORKING/`
   - `REFERENCE/` or `RULES/` only if needed to interpret supplied evidence

Do not load the whole campaign unless the session truly requires it.

## Modes

Choose the mode before writing anything.

### Live Mode

Use for real played-session processing.

Allowed without extra approval:

- create Source Records
- create or update the Session record for the run
- open Working Records when ambiguity or continuity pressure requires them
- draft Event proposals
- generate a pending change set
- generate a processing report

Stop for human approval before:

- activating Events in `CANON/events/`
- applying Entity updates
- applying Relationship updates
- refreshing `STATE/`

### Rehearsal Mode

Use for tests, fake roleplays, simulated chats, dry runs, or "what if this session happened?" exercises.

Rules:

- write only inside `TESTS/skills/process-session/` unless the user explicitly requests a different test location
- never create or modify `CANON/` or `STATE/`
- do not write fake evidence into `SOURCE/`
- treat every output as non-canonical working material
- prefer a single rehearsal packet unless the user explicitly wants full preview files

## Workflow

1. Identify `campaign_ref`, input type, and mode.
2. Preserve the raw input exactly enough to keep ambiguity visible.
3. Create a Source Record or Source Record preview.
4. Create a Session record or Session preview that stays at the observation layer.
5. Open a Working Record only when the session contains ambiguity, contradiction, continuity risk, or interpretation that should not be mistaken for canon.
6. Propose Events as draft world-history claims with explicit provenance.
7. Generate a pending change set or change-set preview.
8. In Live Mode, pause for approval before any canon-affecting write.
9. In Rehearsal Mode, stop after the preview packet and surface review questions.
10. Generate a report that explains the run, touched context, and remaining approval boundary.

## Guardrails

- Keep evidence, observation, interpretation, and canon separate.
- Never import prep-only material as played truth unless the supplied input says it happened.
- Approved future-facing entities may be referenced as existing people, but their scene details still require played evidence before canon changes.
- If the input is partial, contradictory, or secondhand, lower confidence and carry the uncertainty into the Session or Working Record.
- When in doubt, prefer fewer Event proposals with stronger provenance over a complete-sounding but weak packet.

## Output Shape

Aim to produce these artifacts or previews:

- Source Record
- Session
- optional Working Record
- draft Events
- pending change set
- processing report or rehearsal report

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/process-session/fixtures/`
- dry-run outputs live under `TESTS/skills/process-session/runs/`

If a rehearsal touches current campaign material, cite the exact canon or state files that were loaded and note where the rehearsal intentionally diverged into simulation.
