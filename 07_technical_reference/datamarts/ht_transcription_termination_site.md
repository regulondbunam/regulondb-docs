# Datamart: HT Transcription Termination Sites (`transcriptionTerminationSite`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 5,326
- **Size of the BSON file:** 3.8 MB

## Purpose

Transcription termination sites (TTS) identified in HT experiments.

## Used By

GraphQL **HT Transcription Termination Site** queries.

## Source (core collections)

Processed HT data. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 5,326).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"ECOLITT000000001"` |
| `chromosome` | `string` | 100% | `"NC_000913.3"` |
| `closestGenes` | `array` | 100% | `[{"_id": "RDBECOLIGNC00987", "distanceTo": 29.0, "name": "thrA", "p...` |
| `datasetIds` | `array` | 100% | `["RHTECOLITTD00572"]` |
| `leftEndPosition` | `int` | 100% | `308` |
| `rightEndPosition` | `int` | 100% | `308` |
| `strand` | `string` | 100% | `"+"` |
| `temporalId` | `string` | 100% | `"[TTS_TR0001,308,308,+]"` |
| `terminator` | `array` | 100% | `[{"_id": "RDBECOLITMC00051", "transcriptionUnits": [{"_id": "RDBECO...` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `closestGenes` | `_id`, `distanceTo`, `name`, `productName`, `transcriptionUnits` |
| `terminator` | `_id`, `transcriptionUnits` |

## Example (first document, simplified)

```json
{
  "_id": "ECOLITT000000001",
  "chromosome": "NC_000913.3",
  "closestGenes": [
    {
      "_id": "RDBECOLIGNC00987",
      "distanceTo": 29.0,
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
      "distanceTo": 118.0,
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
    "RHTECOLITTD00572"
  ],
  "leftEndPosition": 308,
  "rightEndPosition": 308,
  "strand": "+",
  "temporalId": "[TTS_TR0001,308,308,+]",
  "terminator": [
    {
      "_id": "RDBECOLITMC00051",
      "transcriptionUnits": [
        {
          "_id": "RDBECOLITUC02074",
          "name": "thrL",
          "promoter": {
            "_id": "RDBECOLIPMC03512",
            "leftEndPosition": 148,
            "name": "thrLp",
            "rightEndPosition": 148,
            "sequence": "gccgtgagtaaattaaaattttattgacttaggtcactaaatactttaaccaatataggcAtagcgcacagacagataaaa",
            "strand": "forward"
          }
        }
  ...
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
