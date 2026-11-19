<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Operons (`operons`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 2,605

## Purpose

Stores operon objects with genomic range and strand orientation.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 2,605 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIOPC00272"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "TU...` |
| `internalComment` | `string` |  | 0% |  |  |
| `name` | `string` | yes | 100% |  | `"ycaI-msbA-lpxK-ycaQ"` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `regulationPositions` | `object` | yes | 100% |  | `{"leftEndPosition": 964320, "rightEndPosition": 970621}` |
| `strand` | `string` |  | 100% | values: `forward`, `reverse` | `"forward"` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `regulationPositions` | `leftEndPosition`, `rightEndPosition` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIOPC00272",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "TU0-13087"
    }
  ],
  "name": "ycaI-msbA-lpxK-ycaQ",
  "organisms_id": "RDBECOLIORC00001",
  "regulationPositions": {
    "leftEndPosition": 964320,
    "rightEndPosition": 970621
  },
  "strand": "forward"
}
```

## Main Relationships

- `organisms_id` -> organisms collection
- `externalCrossReferences[].externalCrossReferences_id` -> external cross-reference catalog

## Related Content
- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
