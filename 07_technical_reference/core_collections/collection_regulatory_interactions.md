# Collection: Regulatory Interactions (`regulatoryInteractions`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 6,460

## Purpose

Represents regulatory links between a regulator and a regulated entity (a promoter, a gene, or a transcription unit), including function, confidence level, and supporting citations.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 6,460 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIRIC00001"` |
| `accessoryProteins` | `array<string>` |  | 2% |  | `["RDBECOLIRCC00019"]` |
| `additiveEvidences` | `array<string>` |  | 36% |  | `["RDBECOLIAEC00013"]` |
| `relativeDistSitePromoter` | `number` |  | 54% |  | `-60.5` |
| `citations` | `array<object>` |  | 99% |  | `[{"evidences_id": "RDBECOLIEVC00090", "publications_id": "RDBECOLIP...` |
| `confidenceLevel` | `string` |  | 99% |  | `"W"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "RE...` |
| `function` | `string` |  | 100% | values: `activator`, `repressor`, `dual` | `"repressor"` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `note` | `string` |  | 35% |  | `"The precise position of the CsrA binding site is inferred by its s...` |
| `mechanism` | `array<string>` |  | 2% |  | `["\|MRNA-DEGRADATION\|"]` |
| `regulationClass` | `array<string>` |  | 100% |  | `["\|Transcription-Factor-Binding\|"]` |
| `regulationType` | `string` |  | 100% |  | `"Transcription"` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `regulatedEntity` | `object` |  | 100% |  | `{"_id": "RDBECOLIPMC03434", "name": "slpp", "type": "promoter"}` |
| `regulator` | `object` |  | 100% |  | `{"_id": "RDBECOLIPDC01486", "name": "DNA-binding transcriptional du...` |
| `sequence` | `string` |  | 0% | pattern `^[ATCGatcg]+$` |  |
| `regulatorySites_id` | `string` |  | 90% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIBSC02029"` |
| `type` | `string` |  | 0% | values: `mechanistic`, `physiological` |  |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `regulatedEntity` | `_id`, `name`, `type` |
| `regulator` | `_id`, `name`, `type` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIRIC00001",
  "citations": [
    {
      "evidences_id": "RDBECOLIEVC00090",
      "publications_id": "RDBECOLIPRC02132"
    },
    {
      "publications_id": "RDBECOLIPRC05482"
    }
  ],
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "REG0-10000"
    }
  ],
  "function": "repressor",
  "internalComment": "; Source: EcoCyc",
  "organisms_id": "RDBECOLIORC00001",
  "regulatedEntity": {
    "_id": "RDBECOLIPMC03434",
    "name": "slpp",
    "type": "promoter"
  },
  "regulationClass": [
    "|Transcription-Factor-Binding|"
  ],
  "regulationType": "Transcription",
  "regulator": {
    "_id": "RDBECOLIPDC01486",
    "name": "DNA-binding transcriptional dual regulator GadW",
    "type": "product"
  },
  "regulatorySites_id": "RDBECOLIBSC02029",
  "relativeDistSitePromoter": -60.5
}
```

## Main Relationships

- `regulator._id` -> regulator/product object
- `regulatedEntity._id` -> promoter/TU/other regulated objects
- `regulatorySites_id` -> regulatory sites collection
- `citations[].evidences_id` -> evidences collection

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
