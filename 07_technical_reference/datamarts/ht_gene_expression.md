# Datamart: HT Gene Expression (`geneExpression`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 8,606,088
- **Size of the BSON file:** 2.6 GB

## Purpose

Gene expression values per HT dataset and gene.

## Used By

GraphQL **HT Gene Expression** queries.

## Source (core collections)

Processed expression data. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 8,606,088).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"GENE_EXPRESSION_ERR1218301_b0001"` |
| `count` | `double` | 87% | `134.008417` |
| `datasetIds` | `array` | 100% | `["GENE_EXPRESSION_ERR1218301"]` |
| `gene` | `object` | 96% | `{"_id": "RDBECOLIGNC01250", "bnumber": "b0001", "leftEndPosition": ...` |
| `temporalId` | `string` | 100% | `"GENE_EXPRESSION_ERR1218301_b0001"` |
| `fpkm` | `double` | 84% | |
| `tpm` | `double` | 84% | |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `gene` | `_id`, `bnumber`, `leftEndPosition`, `name`, `rightEndPosition`, `synonyms` |

## Example (first document, simplified)

```json
{
  "_id": "GENE_EXPRESSION_ERR1218301_b0001",
  "count": 134.008417,
  "datasetIds": [
    "GENE_EXPRESSION_ERR1218301"
  ],
  "gene": {
    "_id": "RDBECOLIGNC01250",
    "bnumber": "b0001",
    "leftEndPosition": 190,
    "name": "thrL",
    "rightEndPosition": 255,
    "synonyms": [
      "EG11277"
    ]
  },
  "temporalId": "GENE_EXPRESSION_ERR1218301_b0001"
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
