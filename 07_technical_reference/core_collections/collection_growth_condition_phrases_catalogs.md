# Collection: Growth Condition Phrases Catalogs (`growthConditionPhrasesCatalogs`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** not included in the release export (the collection is defined in the schema but has no data)

## Purpose

Intended to store cataloged phrase resources related to growth condition annotation.

## Fields

Data types and required fields come from the JSON Schema used to validate the collection.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes |  | pattern `^RDB[A-Z]{8}[0-9]{5}$` |  |
| `description` | `string` |  |  |  |  |
| `name` | `string` | yes |  |  |  |
| `terms` | `array<object>` | yes |  |  |  |
| `schemaVersion` | `number` |  |  |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `terms` | `terms_id`, `termType` |

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
