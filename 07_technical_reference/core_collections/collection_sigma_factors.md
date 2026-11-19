# Collection: Sigma Factors (`sigmaFactors`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 7

## Purpose

Stores sigma factor objects used in promoter recognition and transcription initiation context.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 7 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLISFC00001"` |
| `abbreviatedName` | `string` |  | 100% |  | `"sigma28"` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `citations` | `array<object>` |  | 86% |  | `[{"publications_id": "RDBECOLIPRC02068"}, {"publications_id": "RDBE...` |
| `confidenceLevel` | `string` |  | 57% |  | `"W"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00004", "objectId": "P0...` |
| `genes_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIGNC01323"` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `name` | `string` | yes | 100% |  | `"RNA polymerase sigma factor FliA"` |
| `note` | `string` |  | 100% |  | `"&sigma;<sup>28</sup> is a minor sigma factor that is responsible f...` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `synonyms` | `array<string>` |  | 100% |  | `["sigma 28 factor", "sigma 28", "sigma F factor", "FliA", "RNA poly...` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLISFC00001",
  "abbreviatedName": "sigma28",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00004",
      "objectId": "P0AEM6"
    },
    {
      "externalCrossReferences_id": "RDBECOLIERC00001",
      "objectId": "6PMJ"
    },
    "..."
  ],
  "genes_id": "RDBECOLIGNC01323",
  "internalComment": "; Source: EcoCyc",
  "name": "RNA polymerase sigma factor FliA",
  "note": "&sigma;<sup>28</sup> is a minor sigma factor that is responsible for initiation of transcription of a number of genes in...",
  "organisms_id": "RDBECOLIORC00001",
  "synonyms": [
    "sigma 28 factor",
    "sigma 28",
    "..."
  ]
}
```

## Main Relationships

- Referenced by `promoters.bindsSigmaFactor.sigmaFactors_id`
- `genes_id` -> genes collection

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
