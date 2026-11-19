# Datamart: List Page (`listPage`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 7,650
- **Size of the BSON file:** 1.2 MB

## Purpose

Lightweight list of objects (name, synonyms, encoded genes, product names) for the catalogs. `datamartType` values: `gene`, `operon`, `regulon`, `sigmulon`.

## Used By

Catalog tables opened from the **Genes**, **Operon**, **Regulon**, and **Sigmulon** links of the homepage.

## Source (core collections)

Generated from the gene, operon, regulon, and sigmulon datamarts. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 7,650).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLITFC00001"` |
| `datamartType` | `string` | 100% | `"regulon"` |
| `encodedGenes` | `array` | 10% | `["yafC"]` |
| `name` | `string` | 100% | `"YafC"` |
| `productsName` | `array` | 98% | `["DNA-binding transcriptional regulator YafC"]` |
| `synonyms` | `array` | 100% | `["YafC", "predicted DNA-binding transcriptional regulator LYSR-type"]` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLITFC00001",
  "datamartType": "regulon",
  "encodedGenes": [
    "yafC"
  ],
  "name": "YafC",
  "productsName": [
    "DNA-binding transcriptional regulator YafC"
  ],
  "synonyms": [
    "YafC",
    "predicted DNA-binding transcriptional regulator LYSR-type"
  ]
}
```

## Indexes

| Name | Keys |
|---|---|
| `name_1` | `{"name": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
