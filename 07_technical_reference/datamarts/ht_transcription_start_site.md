<img src="../../assets/icons/technical.svg" alt="" width="48">

# Datamart: HT Transcription Start Sites (`transcriptionStartSite`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 68,044
- **Size of the BSON file:** 49.3 MB

## Purpose

Transcription start sites (TSS) identified in HT experiments.

## Used By

GraphQL **HT Transcription Start Site** queries.

## Source (core collections)

Processed HT data. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 68,044).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"ECOLITS000000001"` |
| `chromosome` | `string` | 100% | `"NC_000913.3"` |
| `closestGenes` | `array` | 100% | `[{"_id": "RDBECOLIGNC00987", "distanceTo": 299.0, "name": "thrA", "...` |
| `datasetIds` | `array` | 100% | `["RHTECOLITSD00556"]` |
| `leftEndPosition` | `int` | 100% | `38` |
| `pos_1` | `int` | 100% | `38` |
| `promoter` | `array` | 100% | `[]` |
| `rightEndPosition` | `int` | 100% | `38` |
| `strand` | `string` | 100% | `"+"` |
| `temporalId` | `string` | 100% | `"[TSS_DS0001,38,38,+]"` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `closestGenes` | `_id`, `distanceTo`, `name`, `productName`, `transcriptionUnits` |

## Example (first document, simplified)

```json
{
  "_id": "ECOLITS000000001",
  "chromosome": "NC_000913.3",
  "closestGenes": [
    {
      "_id": "RDBECOLIGNC00987",
      "distanceTo": 299.0,
      "name": "thrA",
      "productName": [
        "fused aspartate kinase/homoserine dehydrogenase 1"
      ],
      "transcriptionUnits": [
        {
          "_id": "RDBECOLITUC03283",
          "name": "thrLABC"
        }
      ]
    },
    {
      "_id": "RDBECOLIGNC01251",
      "distanceTo": 152.0,
      "name": "thrL",
      "productName": [
        "<i>thr</i> operon leader peptide"
      ],
      "transcriptionUnits": [
        {
          "_id": "RDBECOLITUC02074",
          "name": "thrL"
        },
        {
          "_id": "RDBECOLITUC03283",
          "name": "thrLABC"
        }
      ]
    }
  ],
  "datasetIds": [
    "RHTECOLITSD00556"
  ],
  "leftEndPosition": 38,
  "pos_1": 38,
  "promoter": [],
  "rightEndPosition": 38,
  "strand": "+",
  "temporalId": "[TSS_DS0001,38,38,+]"
}
```

## Related Content
- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
