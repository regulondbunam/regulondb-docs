<img src="../../assets/icons/technical.svg" alt="" width="48">

# Datamart: HT Authors Data (`authorsData`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 573
- **Size of the BSON file:** 36.4 MB

## Purpose

Data tables as reported by the authors of each high-throughput (HT) dataset.

## Used By

GraphQL **HT authorsData** queries.

## Source (core collections)

HT dataset curation. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 573 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"ECOLIAD000000001"` |
| `authorsData` | `string` | 100% | `"Protein Name,Peak center in TEC datababase,Peak center,Peak Intens...` |
| `datasetIds` | `array` | 100% | `["RHTECOLIRNP00001"]` |

## Example (first document, simplified)

```json
{
  "_id": "ECOLIAD000000001",
  "authorsData": "Protein Name,Peak center in TEC datababase,Peak center,Peak Intensity Fold Change/Binding intensity (%),Target gene,GCs (Experimental),Evidence for binding (Met...",
  "datasetIds": [
    "RHTECOLIRNP00001"
  ]
}
```

## Related Content
- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
