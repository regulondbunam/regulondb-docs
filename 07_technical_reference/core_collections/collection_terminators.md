# Collection: Terminators (`terminators`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 375

## Purpose

Stores transcription terminator objects, including class, sequence, and termination-site coordinates.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 375 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLITMC00001"` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `class` | `string` | yes | 100% | values: `rho-independent`, `rho-dependent` | `"rho-independent"` |
| `citations` | `array<object>` |  | 97% |  | `[{"publications_id": "RDBECOLIPRC15798"}]` |
| `confidenceLevel` | `string` |  | 0% |  |  |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "AC...` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `note` | `string` |  | 1% |  | `"The terminator sequence  downstream of acrF gene appears to form a...` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `sequence` | `string` | yes | 100% | pattern `^[ATCGatcg]+$` | `"agcgtcaaaaGGCCGGATTTTCCGGCCttttttatta"` |
| `transcriptionTerminationSite` | `object` | yes | 100% |  | `{"leftEndPosition": 3407286, "rightEndPosition": 3407302}` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `transcriptionTerminationSite` | `leftEndPosition`, `rightEndPosition`, `type` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLITMC00001",
  "citations": [
    {
      "publications_id": "RDBECOLIPRC15798"
    }
  ],
  "class": "rho-independent",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "ACCCT1"
    }
  ],
  "internalComment": "; Source: EcoCyc",
  "organisms_id": "RDBECOLIORC00001",
  "sequence": "agcgtcaaaaGGCCGGATTTTCCGGCCttttttatta",
  "transcriptionTerminationSite": {
    "leftEndPosition": 3407286,
    "rightEndPosition": 3407302
  }
}
```

## Main Relationships

- Referenced by `transcriptionUnits.terminators_ids[]`

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
