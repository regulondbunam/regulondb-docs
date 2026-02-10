# Collection: Additive Evidences

## Purpose

Stores additive evidence rules used to derive integrated confidence evidence from combinations of base evidence types.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable additive evidence identifier | `string` | `RDBECOLIAEC00001` |
| `code` | Additive evidence code | `string` | `AE(EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP/COMP-HINF-POSITIONAL-IDENTIFICATION)` |
| `category` | Additive evidence category | `string` | `independent cross-validation` |
| `confidenceLevel` | Resulting confidence level | `string` | `S` |
| `pertainsTo` | Target object categories | `array<string>` | `["Promoters"]` |
| `rules` | Internal rule references | `array<number>` | `[10, 7]` |
| `evidenceIds` | Linked base evidence IDs | `array<string>` | `["RDBECOLIEVC00051", "RDBECOLIEVC00034"]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIAEC00001",
  "category": "independent cross-validation",
  "confidenceLevel": "S",
  "evidenceIds": ["RDBECOLIEVC00051", "RDBECOLIEVC00034"]
}
```

## Main Relationships

- `evidenceIds[]` -> evidences collection

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
