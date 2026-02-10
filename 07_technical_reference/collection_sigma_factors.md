# Collection: Sigma Factors

## Purpose

Stores sigma factor objects used in promoter recognition and transcription initiation context.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable sigma-factor identifier | `string` | `RDBECOLISFC00001` |
| `name` | Full sigma factor name | `string` | `RNA polymerase sigma factor FliA` |
| `abbreviatedName` | Short sigma symbol | `string` | `sigma28` |
| `genes_id` | Linked coding gene identifier | `string` | `RDBECOLIGNC01323` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `synonyms` | Alternative names | `array<string>` | `["FliA", "RpoF"]` |
| `note` | Curated biological note | `string` | `sigma28 is a minor sigma factor...` |
| `externalCrossReferences` | External mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00059","objectId":"P0AEM6"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLISFC00001",
  "abbreviatedName": "sigma28",
  "genes_id": "RDBECOLIGNC01323",
  "organisms_id": "RDBECOLIORC00001"
}
```

## Main Relationships

- Referenced by `promoters.bindsSigmaFactor.sigmaFactors_id`
- `genes_id` -> genes collection

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
