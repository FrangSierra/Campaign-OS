# Campaign OS Invariants

## Purpose

This document defines the properties that must always remain true for a valid Campaign OS installation and a valid campaign dataset.

Operational procedures may evolve. Templates may evolve. Workflows may evolve. These invariants do not.

## Core Invariants

1. Every persistent record has one stable globally unique identifier.
2. Every persistent record declares its record type explicitly.
3. Every canonical claim is traceable to evidence or explicit human approval.
4. Source Records preserve evidence and remain append-only in substance.
5. Sessions record observed play and do not replace canonical world history.
6. Events are the authoritative unit of canonical world-history truth.
7. Entity and Relationship updates must be supportable from approved events.
8. Working Records are never canonical.
9. Derived State is reproducible, non-canonical, and never manually authoritative.
10. Generated artifacts may improve usability but may never become hidden dependencies for campaign portability.
11. Campaign data must remain usable without generated helpers.
12. Skills, commands, workflows, and tasks may never bypass the Truth Pipeline.
13. Contradictions are resolved through preserved provenance, not silent overwrite.
14. Human approval is required before canon-affecting changes are applied unless an explicit operating rule delegates that authority.

## Truth Pipeline Invariants

The Campaign OS MVP Truth Pipeline is:

Source Record  
-> Session  
-> Working Record (optional)  
-> Proposed Event  
-> Human Approval  
-> Entity and Relationship updates  
-> Derived State update  
-> Processing Report

The following must remain true:

- evidence enters the system through Source Records
- observed play becomes Session records before canon proposals
- ambiguity may be handled in Working Records
- canonical truth is proposed through Events
- approval happens before canon-affecting updates
- derived state is produced after canonical changes, not before
- reports describe processing outcomes and do not define truth

## Portability Invariants

Campaign data must remain portable across tools and runtimes.

This means:

- Markdown records remain canonical
- binary assets remain directly referenceable
- a campaign can be moved without requiring indexes, caches, or vendor-specific systems
- repository structure may assist operations but may not conceal the source of truth

## Runtime Invariants

Any AI operating inside Campaign OS must:

- follow [AI_RUNTIME.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SYSTEM/AI_RUNTIME.md)
- preserve provenance
- classify writes conservatively
- stop rather than invent facts
- prefer the smaller safe change over the larger clever one

## Review Notes

New invariants should be added only when they are universally true across the system. If a rule applies only to one workflow or one record type, it belongs elsewhere.
