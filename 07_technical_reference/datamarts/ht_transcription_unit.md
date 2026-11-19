# Datamart: HT Transcription Units (`transcriptionUnit`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 12,329
- **Size of the BSON file:** 4.9 MB

## Purpose

Transcription units identified in HT experiments.

## Used By

GraphQL **HT Transcription Unit** queries.

## Source (core collections)

Processed HT data. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 12,329).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"ECOLITU000000001"` |
| `chromosome` | `string` | 100% | `"NC_000913.3"` |
| `datasetIds` | `array` | 100% | `["RHTECOLITUD00577"]` |
| `genes` | `array` | 100% | `[{"_id": "RDBECOLIGNC01250", "bnumber": "b0001", "name": "thrL"}]` |
| `leftEndPosition` | `int` | 100% | `147` |
| `length` | `int` | 100% | `162` |
| `name` | `string / null` | 100% | `"thrL"` |
| `phantom` | `int` | 100% | `0` |
| `pseudo` | `int` | 100% | `0` |
| `rightEndPosition` | `int` | 100% | `308` |
| `strand` | `string` | 100% | `"+"` |
| `temporalId` | `string` | 100% | `"[TUS_TU0001,147,308,+]"` |
| `termType` | `string` | 100% | `"TTS"` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `genes` | `_id`, `bnumber`, `name` |

## Example (first document, simplified)

```json
{
  "_id": "ECOLITU000000001",
  "chromosome": "NC_000913.3",
  "datasetIds": [
    "RHTECOLITUD00577"
  ],
  "genes": [
    {
      "_id": "RDBECOLIGNC01250",
      "bnumber": "b0001",
      "name": "thrL"
    }
  ],
  "leftEndPosition": 147,
  "length": 162,
  "name": "thrL",
  "phantom": 0,
  "pseudo": 0,
  "rightEndPosition": 308,
  "strand": "+",
  "temporalId": "[TUS_TU0001,147,308,+]",
  "termType": "TTS"
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
