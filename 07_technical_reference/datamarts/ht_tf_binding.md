<img src="../../assets/icons/technical.svg" alt="" width="48">

# Datamart: HT TF Binding (`tfBinding`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 3,142
- **Size of the BSON file:** 2.6 MB

## Purpose

Transcription factor binding sites identified in HT experiments.

## Used By

GraphQL **HT TFBinding** queries.

## Source (core collections)

Processed HT data. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 3,142).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"ECOLIBS000000001"` |
| `chrLeftPosition` | `int` | 100% | `97103` |
| `chrRightPosition` | `int` | 100% | `97122` |
| `chromosome` | `string` | 100% | `"NC_000913.3"` |
| `closestGenes` | `array` | 100% | `[{"_id": "RDBECOLIGNC00613", "distanceTo": 25.5, "name": "murD", "p...` |
| `datasetIds` | `array` | 100% | `["RHTECOLIBSD00224"]` |
| `foundRIs` | `array` | 100% | `[]` |
| `nameCollection` | `string` | 100% | `"CHIP_SEQ"` |
| `peakId` | `string` | 100% | `"ECOLIPK000000008"` |
| `score` | `double` | 100% | `7.1` |
| `sequence` | `string` | 100% | `"TAAAAATGTCGTCATTATC"` |
| `strand` | `string` | 100% | `"+"` |
| `temporalId` | `string` | 100% | `"[97103,97122,7.1,+,TAAAAATGTCGTCATTATC]"` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `closestGenes` | `_id`, `distanceTo`, `name`, `productName`, `transcriptionUnits` |
| `foundRIs` | `_id`, `citations`, `origin`, `relativeGeneDistance`, `relativeTSSDistance`, `sequence`, `strand`, `tfbsLeftPosition`, `tfbsRightPosition` |

## Example (first document, simplified)

```json
{
  "_id": "ECOLIBS000000001",
  "chrLeftPosition": 97103,
  "chrRightPosition": 97122,
  "chromosome": "NC_000913.3",
  "closestGenes": [
    {
      "_id": "RDBECOLIGNC00613",
      "distanceTo": 25.5,
      "name": "murD",
      "productName": [
        "UDP-<i>N</i>-acetylmuramoyl-L-alanine&mdash;D-glutamate ligase"
      ],
      "transcriptionUnits": [
        {
          "_id": "RDBECOLITUC01544",
          "name": "rsmH-ftsLIO-murEF-mraY-murD-ftsW-murGC-ddlB-ftsQAZ-lpxC"
        },
        {
          "_id": "RDBECOLITUC01545",
          "name": "ftsLIO-murEF-mraY-murD-ftsW-murGC-ddlB-ftsQAZ-lpxC"
        },
        "..."
      ]
    }
  ],
  "datasetIds": [
    "RHTECOLIBSD00224"
  ],
  "foundRIs": [],
  "nameCollection": "CHIP_SEQ",
  "peakId": "ECOLIPK000000008",
  "score": 7.1,
  "sequence": "TAAAAATGTCGTCATTATC",
  "strand": "+",
  "temporalId": "[97103,97122,7.1,+,TAAAAATGTCGTCATTATC]"
}
```

## Related Content
- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
