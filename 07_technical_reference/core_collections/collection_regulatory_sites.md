# Collection: Regulatory Sites (`regulatorySites`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 4,647

## Purpose

Stores regulatory binding sites with genomic coordinates, sequence, and confidence/citation support.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 4,647 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIBSC00001"` |
| `absolutePosition` | `number` |  | 78% |  | `1825774.5` |
| `additiveEvidences` | `array<string>` |  | 9% |  | `["RDBECOLIAEC00013"]` |
| `citations` | `array<object>` |  | 93% |  | `[{"publications_id": "RDBECOLIPRC03396"}, {"evidences_id": "RDBECOL...` |
| `confidenceLevel` | `string` |  | 92% |  | `"S"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "BS...` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `leftEndPosition` | `number` |  | 85% |  | `1825765` |
| `length` | `number` |  | 97% |  | `20` |
| `note` | `string` |  | 24% |  | `"MarA represses <i>rob</i> by steric hindrance \|CITS:[20453091]\|....` |
| `regulationType` | `string` |  | 100% |  | `"Transcription"` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `rightEndPosition` | `number` |  | 85% |  | `1825784` |
| `sequence` | `string` |  | 84% | pattern `^[ATCGatcg]+$` | `"cacttttgcgCCAATTATGGAGAAAAAAAGaaaatttgat"` |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIBSC00001",
  "absolutePosition": 1825774.5,
  "citations": [
    {
      "publications_id": "RDBECOLIPRC03396"
    },
    {
      "evidences_id": "RDBECOLIEVC00034",
      "publications_id": "RDBECOLIPRC03396"
    },
    "..."
  ],
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "BS-7046"
    }
  ],
  "internalComment": "; Source: EcoCyc",
  "leftEndPosition": 1825765,
  "length": 20,
  "organisms_id": "RDBECOLIORC00001",
  "regulationType": "Transcription",
  "rightEndPosition": 1825784,
  "sequence": "cacttttgcgCCAATTATGGAGAAAAAAAGaaaatttgat",
  "confidenceLevel": "S"
}
```

## Main Relationships

- Referenced by `regulatoryInteractions.regulatorySites_id`
- `citations[].evidences_id` -> evidences collection
- `citations[].publications_id` -> publications collection

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
