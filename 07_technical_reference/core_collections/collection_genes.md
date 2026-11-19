<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Genes (`genes`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 4,748

## Purpose

Stores core gene objects with genomic coordinates, sequence, and cross-references.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 4,748 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIGNC00001"` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `bnumber` | `string` |  | 99% |  | `"b4053"` |
| `centisomePosition` | `number` |  | 100% |  | `91.90224` |
| `citations` | `array<object>` |  | 5% |  | `[{"publications_id": "RDBECOLIPRC11034"}, {"publications_id": "RDBE...` |
| `confidenceLevel` | `string` |  | 0% |  |  |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00006", "objectId": "EC...` |
| `fragments` | `array<object>` |  | 0% |  | `[{"centisomePosition": 12.404764, "id": "\|GFRAG0-25\|", "leftEndPo...` |
| `gcContent` | `number` |  | 100% |  | `55.925925925925924` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `interrupted` | `boolean` |  | 0% |  | `true` |
| `leftEndPosition` | `number` |  | 100% |  | `4265782` |
| `name` | `string` |  | 100% |  | `"alr"` |
| `note` | `string` |  | 2% |  | `"\n"` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `rightEndPosition` | `number` |  | 100% |  | `4266861` |
| `sequence` | `string` |  | 100% | pattern `^[ATCGatcg]+$` | `"ATGCAAGCGGCAACTGTTGTGATTAACCGCCGCGCTCTGCGACACAACCTGCAACGTCTTCGTGAA...` |
| `strand` | `string` |  | 100% | values: `forward`, `reverse` | `"forward"` |
| `synonyms` | `array<string>` |  | 100% |  | `["alr5", "EG10001"]` |
| `terms` | `array<object>` |  | 0% |  |  |
| `type` | `string` |  | 4% | values: `pseudo`, `phantom`, `gene`, `truncated` | `"pseudo"` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `fragments` | `id`, `strand`, `name`, `leftEndPosition`, `rightEndPosition`, `sequence`, `centisomePosition` |
| `terms` | `terms_id`, `terms_name`, `termLabel`, `parents` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIGNC00001",
  "bnumber": "b4053",
  "centisomePosition": 91.90224,
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00006",
      "objectId": "ECK4045+b4053+JW4013+alr"
    },
    {
      "externalCrossReferences_id": "RDBECOLIERC00026",
      "objectId": "ECK4045+b4053+JW4013+alr"
    },
    "..."
  ],
  "gcContent": 55.925925925925924,
  "internalComment": "; Source: EcoCyc",
  "leftEndPosition": 4265782,
  "name": "alr",
  "organisms_id": "RDBECOLIORC00001",
  "rightEndPosition": 4266861,
  "sequence": "ATGCAAGCGGCAACTGTTGTGATTAACCGCCGCGCTCTGCGACACAACCTGCAACGTCTTCGTGAACTGGCCCCTGCCAGTAAAATGGTTGCGGTGGTGAAAGCGAACGCTTATGGTCAC...",
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
