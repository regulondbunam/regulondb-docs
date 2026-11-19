<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Growth Condition Contrasts (`growthConditionContrasts`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** not included in the release export (the collection is defined in the schema but has no data)

## Purpose

Stores contrasts/comparisons between growth conditions when available.

## Fields

Data types and required fields come from the JSON Schema used to validate the collection.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes |  | pattern `^RDB[A-Z]{8}[0-9]{5}$` |  |
| `control_gc_phrases_id` | `string` | yes |  | pattern `^RDB[A-Z]{8}[0-9]{5}$` |  |
| `experimental_gc_phrases_id` | `string` | yes |  | pattern `^RDB[A-Z]{8}[0-9]{5}$` |  |
| `note` | `string` |  |  |  |  |
| `results` | `array<object>` |  |  |  |  |
| `variable` | `string` |  |  |  |  |
| `schemaVersion` | `number` |  |  |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `results` | `identifiers_id`, `identifiers_type`, `effect`, `note` |

## Related Content
- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
