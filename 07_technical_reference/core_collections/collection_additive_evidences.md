<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Additive Evidences (`additiveEvidences`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 353

## Purpose

Stores additive evidence rules used to derive integrated confidence evidence from combinations of base evidence types.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 353 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIAEC00001"` |
| `code` | `string` |  | 100% |  | `"AE(EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP/COMP-HINF-POSITIONAL-IDENTI...` |
| `category` | `string` |  | 100% |  | `"independent cross-validation"` |
| `confidenceLevel` | `string` |  | 100% |  | `"S"` |
| `pertainsTo` | `array<string>` |  | 100% |  | `["Promoters"]` |
| `rules` | `array<number>` |  | 100% |  | `[10, 7]` |
| `evidenceIds` | `array<string>` |  | 100% |  | `["RDBECOLIEVC00062", "RDBECOLIEVC00012"]` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIAEC00001",
  "code": "AE(EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP/COMP-HINF-POSITIONAL-IDENTIFICATION)",
  "category": "independent cross-validation",
  "confidenceLevel": "S",
  "pertainsTo": [
    "Promoters"
  ],
  "rules": [
    10,
    7
  ],
  "evidenceIds": [
    "RDBECOLIEVC00062",
    "RDBECOLIEVC00012"
  ]
}
```

## Main Relationships

- `evidenceIds[]` -> evidences collection

## Related Content
- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
