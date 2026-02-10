# Collection: Transcription Units

## Purpose

Represents transcription units (TUs) and links to promoters, operons, genes, and terminators.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable TU identifier | `string` | `RDBECOLITUC03781` |
| `name` | TU name/label | `string` | `spy` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `operons_id` | Linked operon identifier | `string` | `RDBECOLIOPC02195` |
| `promoters_id` | Linked promoter identifier | `string` | `RDBECOLIPMC00001` |
| `genes_ids` | Genes contained in TU | `array<string>` | `["RDBECOLIGNC03790"]` |
| `terminators_ids` | Terminators associated with TU | `array<string>` | `["RDBECOLITMC00026"]` |
| `confidenceLevel` | Confidence label | `string` | `S` |
| `citations` | Supporting evidence/publication links | `array<object>` | `[{"evidences_id":"RDBECOLIEVC00060"}]` |
| `note` | Curated biological note | `string` | `"<i>spy</i> gene expression is induced..."` |

## Example (simplified)

```json
{
  "_id": "RDBECOLITUC03781",
  "name": "spy",
  "operons_id": "RDBECOLIOPC02195",
  "promoters_id": "RDBECOLIPMC00001",
  "genes_ids": ["RDBECOLIGNC03790"],
  "terminators_ids": ["RDBECOLITMC00026"],
  "confidenceLevel": "S"
}
```

## Main Relationships

- `operons_id` -> operons collection
- `promoters_id` -> promoters collection
- `genes_ids[]` -> genes collection
- `terminators_ids[]` -> terminators collection
- `citations[]` -> evidences/publications

## Notes

- TUs are a key bridge between structural and regulatory layers.
- TU notes may include rich biological context and citation tags.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
