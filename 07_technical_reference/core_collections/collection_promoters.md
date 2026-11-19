<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Promoters (`promoters`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 4,057

## Purpose

Stores promoter objects, sigma-factor association, sequence boxes, and transcription start site (TSS) information.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 4,057 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIPMC00001"` |
| `additiveEvidences` | `array<string>` |  | 2% |  | `["RDBECOLIAEC00001"]` |
| `bindsSigmaFactor` | `object` |  | 82% |  | `{"sigmaFactors_id": "RDBECOLISFC00003"}` |
| `boxes` | `array<object>` |  | 81% |  | `[{"leftEndPosition": 1825694, "rightEndPosition": 1825699, "sequenc...` |
| `distanceToGene` | `number` |  | 51% |  | `63` |
| `citations` | `array<object>` |  | 100% |  | `[{"evidences_id": "RDBECOLIEVC00036", "publications_id": "RDBECOLIP...` |
| `confidenceLevel` | `string` |  | 99% |  | `"S"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "PM...` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `name` | `string` |  | 100% |  | `"spyp"` |
| `note` | `string` |  | 61% |  | `"This promoter appears to be induced in two phases after &sigma;E i...` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `score` | `number` |  | 44% |  | `4.51` |
| `sequence` | `string` |  | 98% | pattern `^[ATCGatcg]+$` | `"acactttcattgttttaccgttgctctgattaattgacgctaaagtcagtaaagttaatcTcgtca...` |
| `strand` | `string` |  | 100% | values: `forward`, `reverse` | `"reverse"` |
| `synonyms` | `array<string>` |  | 16% |  | `["yfgCp1"]` |
| `transcriptionStartSite` | `object` |  | 98% |  | `{"leftEndPosition": 1825688, "range": 1, "rightEndPosition": 1825688}` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `bindsSigmaFactor` | `citations`, `sigmaFactors_id` |
| `boxes` | `leftEndPosition`, `rightEndPosition`, `sequence`, `type` |
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `transcriptionStartSite` | `leftEndPosition`, `rightEndPosition`, `range`, `type` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIPMC00001",
  "bindsSigmaFactor": {
    "sigmaFactors_id": "RDBECOLISFC00003"
  },
  "boxes": [
    {
      "leftEndPosition": 1825694,
      "rightEndPosition": 1825699,
      "sequence": "TAAAGT",
      "type": "minus10"
    },
    {
      "leftEndPosition": 1825715,
      "rightEndPosition": 1825720,
      "sequence": "ATTAAT",
      "type": "minus35"
    }
  ],
  "citations": [
    {
      "evidences_id": "RDBECOLIEVC00036",
      "publications_id": "RDBECOLIPRC02651"
    },
    {
      "publications_id": "RDBECOLIPRC04231"
    },
    "..."
  ],
  "distanceToGene": 63,
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "PM-8764"
    }
  ],
  "internalComment": "; Source: EcoCyc",
  "name": "spyp",
  "organisms_id": "RDBECOLIORC00001",
  "sequence": "acactttcattgttttaccgttgctctgattaattgacgctaaagtcagtaaagttaatcTcgtcaacacggcacgctact",
  "strand": "reverse",
  "transcriptionStartSite": {
    "leftEndPosition": 1825688,
    "range": 1,
    "rightEndPosition": 1825688
  }
}
```

## Main Relationships

- `bindsSigmaFactor.sigmaFactors_id` -> sigmaFactors collection
- `citations[].evidences_id` -> evidences collection
- `citations[].publications_id` -> publications collection

## Related Content
- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
