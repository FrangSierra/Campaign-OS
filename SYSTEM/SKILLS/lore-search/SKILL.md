---
name: lore-search
description: Use when the user wants a grounded lore answer from the Campaign OS repository, with cited file references and clear separation between canon, derived state, working prep, and evidence. This skill performs disciplined repo search and synthesis without pretending summaries are the same as source truth.
---

# Lore Search

This skill is a repository-aware search and synthesis wrapper. It does not replace `rg`, structured markdown, or direct file reading; it uses them carefully and returns a clear answer with provenance.

## Read First

Load only the minimum safe context:

1. `SYSTEM/AI_RUNTIME.md`
2. `SYSTEM/INVARIANTS.md`
3. `CAMPAIGNS/<campaign-id>/CAMPAIGN.md`
4. then search the smallest relevant subset of:
   - `CANON/`
   - `STATE/`
   - `WORKING/`
   - `REFERENCE/`
   - `SOURCE/` only when the user needs evidentiary detail

Expand in that order only as needed by the question.

## Purpose

This skill is strongest when the user asks for:

- "What do we know about X?"
- a quick recap with citations
- where a topic appears across canon, state, and prep
- a search that distinguishes established truth from planned or speculative material
- a lore answer without loading the whole campaign

## Core Responsibilities

- start with exact or close textual search
- expand context progressively instead of loading everything
- separate canon, derived state, working prep, and evidence in the final answer
- provide file citations for every meaningful claim
- say when the repo does not support a confident answer

## Modes

Choose the narrowest mode that fits the request.

### Exact Search Mode

Use when the user has a name, term, file, or phrase.

Produce:

- direct hits
- best files to open
- concise answer with citations

### Concept Search Mode

Use when the user has a broader question, partial memory, or linked concept cluster.

Focus on:

- the strongest direct files first
- nearby related records
- distinctions between canon and prep

### Recap Mode

Use when the user wants a short briefing on a topic before play.

Focus on:

- what is firmly established
- what remains unresolved
- what prep is currently assuming

## Workflow

1. Identify the exact terms or concept cluster behind the query.
2. Search the smallest relevant scope first, usually with repo search tools.
3. Open only the strongest hits needed to answer the question.
4. Organize findings by truth layer:
   - canon
   - derived state
   - working or prep
   - evidence only if needed
5. If the answer requires inference, label it clearly as inference from loaded files.
6. Return a concise answer with citations and any remaining uncertainty.

## Output Shape

Prefer sections like:

- scope
- files searched or loaded
- canon answer
- state summary
- prep or working notes
- open uncertainty

## Guardrails

- Search results are navigation aids, not truth by themselves.
- Do not let a working note outrank canon.
- Do not flatten evidence, session summary, and derived state into one blended answer.
- If the topic appears only in prep, say so directly.
- When the corpus is small enough for exact search, prefer that over vague semantic paraphrase.

## Test Harness

For local rehearsals in this repo:

- fixtures live under `TESTS/skills/lore-search/fixtures/`
- search packets live under `TESTS/skills/lore-search/runs/`

Use anonymized fixtures that require a cited answer spanning canon, derived state, working prep, and unresolved uncertainty.
