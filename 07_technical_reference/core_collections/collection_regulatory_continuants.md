# Collection: Regulatory Continuants (`regulatoryContinuants`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 114

## Purpose

Stores regulatory continuants (for example metabolites and small molecules) linked to regulation context.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 114 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLICNC00001"` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `citations` | `array<object>` |  | 5% |  | `[{"publications_id": "RDBECOLIPRC17584"}]` |
| `confidenceLevel` | `string` |  | 0% |  |  |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00003", "objectId": "ZI...` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `isRegulator` | `boolean` |  | 1% |  | `true` |
| `name` | `string` | yes | 100% |  | `"(<i>S</i>)-2-acetolactate"` |
| `note` | `string` |  | 26% |  | `"&gamma;-aminobutyrate (GABA) is a four-carbon non-protein amino ac...` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `synonyms` | `array<string>` |  | 88% |  | `["(<i>S</i>)-2-hydroxy-2-methyl-3-oxobutanoate", "&alpha;-acetolact...` |
| `type` | `string` |  | 96% | values: `metabolite`, `protein` | `"metabolite"` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLICNC00001",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00003",
      "objectId": "ZINC000000895425"
    },
    {
      "externalCrossReferences_id": "RDBECOLIERC00051",
      "objectId": "cpd19047"
    },
    "..."
  ],
  "internalComment": "; Source: EcoCyc",
  "name": "(<i>S</i>)-2-acetolactate",
  "organisms_id": "RDBECOLIORC00001",
  "synonyms": [
    "(<i>S</i>)-2-hydroxy-2-methyl-3-oxobutanoate",
    "&alpha;-acetolactate",
    "..."
  ],
  "type": "metabolite"
}
```

## Main Relationships

- `organisms_id` -> organisms collection
- `externalCrossReferences[].externalCrossReferences_id` -> external cross-reference catalog

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
