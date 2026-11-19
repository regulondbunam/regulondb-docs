# Collection: Transcription Units (`transcriptionUnits`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 3,767

## Purpose

Represents transcription units (TUs) and links to promoters, operons, genes, and terminators.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 3,767 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLITUC00001"` |
| `additiveEvidences` | `array<string>` |  | 1% |  | `["RDBECOLIAEC00352"]` |
| `citations` | `array<object>` |  | 96% |  | `[{"publications_id": "RDBECOLIPRC03396"}, {"evidences_id": "RDBECOL...` |
| `confidenceLevel` | `string` |  | 89% |  | `"S"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "TU...` |
| `genes_ids` | `array<string>` | yes | 100% |  | `["RDBECOLIGNC03824"]` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `name` | `string` |  | 100% |  | `"spy"` |
| `note` | `string` |  | 34% |  | `"<i>spy</i> gene expression is induced separately by both copper an...` |
| `promoters_id` | `string` |  | 63% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIPMC00001"` |
| `operons_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIOPC01548"` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `terminators_ids` | `array<string>` |  | 16% |  | `["RDBECOLITMC00026"]` |
| `synonyms` | `array<string>` |  | 14% |  | `["yfgCD"]` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLITUC00001",
  "citations": [
    {
      "publications_id": "RDBECOLIPRC03396"
    },
    {
      "evidences_id": "RDBECOLIEVC00083",
      "publications_id": "RDBECOLIPRC03396"
    },
    "..."
  ],
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "TU-8381"
    }
  ],
  "genes_ids": [
    "RDBECOLIGNC03824"
  ],
  "internalComment": "; Source: EcoCyc",
  "name": "spy",
  "note": "<i>spy</i> gene expression is induced separately by both copper and zinc metals through the CpxAR and BaeSR sensor respo...",
  "operons_id": "RDBECOLIOPC01548",
  "organisms_id": "RDBECOLIORC00001",
  "promoters_id": "RDBECOLIPMC00001",
  "terminators_ids": [
    "RDBECOLITMC00026"
  ],
  "confidenceLevel": "S"
}
```

## Main Relationships

- `operons_id` -> operons collection
- `promoters_id` -> promoters collection
- `genes_ids[]` -> genes collection
- `terminators_ids[]` -> terminators collection
- `citations[]` -> evidences/publications

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
