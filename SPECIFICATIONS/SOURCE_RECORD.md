# Purpose

Source Record preserves incoming evidence at the start of the Truth Pipeline. It keeps the evidentiary basis recoverable before interpretation or canonization.

# Inherits

[BASE_RECORD.md](/Users/durdin/Projects/Durdin/tal-dore-tales/SPECIFICATIONS/BASE_RECORD.md)

# Adds

- campaign scope
- source media classification
- source handling status
- evidence origin
- evidence payload

# Required Fields

- `campaign_ref`
- `source_kind`
- `source_status`
- `captured_from`
- `evidence_payload`

# Optional Fields

- `captured_at_source_time`
- `session_hint`
- `transcription_notes`
- `quality_notes`
- `import_context`

# Constraints

- `campaign_ref` resolves to one Campaign.
- `source_kind` is one of `notes`, `images`, `audio`, `transcripts`, `pdf`, or `imports`.
- `source_status` is one of `captured`, `reviewed`, `interpreted`, `superseded`, or `archived`.
- `evidence_payload` is not empty.
- Source Records do not present unsupported canon as fact.
- Original evidence remains recoverable after transcription, OCR, or annotation.

# References

- Campaign
- Session
- Working Record
- Event
