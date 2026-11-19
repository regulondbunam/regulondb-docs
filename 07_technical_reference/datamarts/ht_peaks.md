# Datamart: HT Peaks (`peaks`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 20,990
- **Size of the BSON file:** 14.7 MB

## Purpose

Peaks from ChIP-type HT experiments, with coordinates and scores.

## Used By

GraphQL **HT Peaks** queries.

## Source (core collections)

Processed HT data. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 20,990).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"ECOLIPK000000001"` |
| `chromosome` | `string` | 100% | `"NC_000913.3"` |
| `closestGenes` | `array` | 100% | `[{"_id": "RDBECOLIGNC00367", "distanceTo": 463.0, "name": "mokC", "...` |
| `datasetIds` | `array` | 100% | `["RHTECOLIBSD00224"]` |
| `name` | `string` | 100% | `"DS00017_peak_1"` |
| `peakLeftPosition` | `int` | 100% | `16382` |
| `peakRightPosition` | `int` | 100% | `16612` |
| `score` | `double` | 100% | `570.0` |
| `siteIds` | `array` | 100% | `[]` |
| `temporalId` | `string` | 100% | `"DS00017_peak_1"` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `closestGenes` | `_id`, `distanceTo`, `name`, `productName`, `transcriptionUnits` |

## Example (first document, simplified)

```json
{
  "_id": "ECOLIPK000000001",
  "chromosome": "NC_000913.3",
  "closestGenes": [
    {
      "_id": "RDBECOLIGNC00367",
      "distanceTo": 463.0,
      "name": "mokC",
      "productName": [
        "regulatory protein MokC"
      ],
      "transcriptionUnits": [
        {
          "_id": "RDBECOLITUC00088",
          "name": "mokC-hokC"
        }
      ]
    },
    {
      "_id": "RDBECOLIGNC02965",
      "distanceTo": 406.0,
      "name": "hokC",
      "productName": [
        "small toxic polypeptide HokC"
      ],
      "transcriptionUnits": [
        {
          "_id": "RDBECOLITUC00088",
          "name": "mokC-hokC"
        }
      ]
    },
    "..."
  ],
  "datasetIds": [
    "RHTECOLIBSD00224"
  ],
  "name": "DS00017_peak_1",
  "peakLeftPosition": 16382,
  "peakRightPosition": 16612,
  "score": 570.0,
  "siteIds": [],
  "temporalId": "DS00017_peak_1"
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
