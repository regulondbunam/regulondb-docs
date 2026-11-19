# Collection: Motifs (`motifs`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 30,339

## Purpose

Stores motifs and features of gene products (for example, signal sequences and domains), with their class, their position in the product sequence, and the product they belong to.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 30,339 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIMTC00002"` |
| `alternateSequence` | `string` |  | 30% |  | `"R"` |
| `attachedGroup` | `string` |  | 3% |  | `"FAD"` |
| `class` | `string` |  | 100% |  | `"Signal-Sequence"` |
| `color` | `string` |  | 100% |  | `"brown"` |
| `dataSource` | `string` |  | 92% |  | `"UniProt 2015-08"` |
| `description` | `string` |  | 4% |  | `"KTN domain"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "FT...` |
| `homologyMotif` | `string` |  | 0% |  | `"PSRM"` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `leftEndPosition` | `number` |  | 100% |  | `1` |
| `note` | `string` |  | 75% |  | `"cytoplasmic rhodanese domain"` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `products_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIPDC01048"` |
| `rightEndPosition` | `number` |  | 100% |  | `22` |
| `sequence` | `string` |  | 100% |  | `"KLLKVAAIAAIVFSGSALAGV"` |
| `residueNumber` | `array<number>` |  | 0% |  | `[56, 58, 85, 147, 256]` |
| `synonyms` | `array<string>` |  | 0% |  |  |
| `type` | `string` |  | 0% |  |  |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIMTC00002",
  "class": "Signal-Sequence",
  "color": "brown",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "FTR-592"
    }
  ],
  "internalComment": "; Source: EcoCyc",
  "leftEndPosition": 1,
  "organisms_id": "RDBECOLIORC00001",
  "products_id": "RDBECOLIPDC01048",
  "rightEndPosition": 22,
  "sequence": "KLLKVAAIAAIVFSGSALAGV"
}
```

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
