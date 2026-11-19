# Collection: Regulatory Complexes (`regulatoryComplexes`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 228

## Purpose

Stores regulatory or functional complexes composed of products, including stoichiometry and contextual notes.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 228 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIRCC00001"` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `abbreviatedName` | `string` |  | 17% |  | `"AccB"` |
| `citations` | `array<object>` |  | 82% |  | `[{"publications_id": "RDBECOLIPRC02673"}, {"publications_id": "RDBE...` |
| `confidenceLevel` | `string` |  | 73% |  | `"S"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "AC...` |
| `function` | `string` |  | 0% |  |  |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `isTranscriptionFactor` | `boolean` |  | 0% |  |  |
| `name` | `string` |  | 100% |  | `"biotin carboxyl carrier protein (dimer)"` |
| `note` | `string` |  | 53% |  | `"Acetyl-CoA carboxyltransferase (ACC) is part of the acetyl-CoA car...` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `products` | `array<object>` |  | 100% |  | `[{"coefficient": 2, "products_id": "RDBECOLIPDC00223"}, {"coefficie...` |
| `regulatoryContinuants_ids` | `array<string>` |  | 59% |  | `["RDBECOLICNC00082"]` |
| `synonyms` | `array<string>` |  | 0% |  |  |
| `type` | `string` |  | 100% | values: `active`, `inactive` | `"active"` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `products` | `products_id`, `coefficient` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIRCC00001",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "ACETYL-COA-CARBOXYLTRANSFER-CPLX"
    }
  ],
  "internalComment": "; Source: EcoCyc",
  "note": "Acetyl-CoA carboxyltransferase (ACC) is part of the acetyl-CoA carboxylase complex, catalyzing the second half-reaction,...",
  "organisms_id": "RDBECOLIORC00001",
  "products": [
    {
      "coefficient": 2,
      "products_id": "RDBECOLIPDC00223"
    },
    {
      "coefficient": 2,
      "products_id": "RDBECOLIPDC00224"
    }
  ],
  "type": "active"
}
```

## Main Relationships

- `products[].products_id` -> products collection
- `organisms_id` -> organisms collection

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
