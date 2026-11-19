# Datamart: Gene Coexpressions (`geneCoexpressions`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 9,316,077
- **Size of the BSON file:** 2.0 GB

## Purpose

Pairwise gene coexpression values: gene pairs with their coexpression rank and display color.

## Used By

GraphQL **Coexpression** tool queries; coexpression browser.

## Source (core collections)

Coexpression matrix (see Credits: Dr. Lucie Pannier). *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 9,316,077).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `ObjectId` | 100% | `"6a8ca26f7d4712e7e5f398e5"` |
| `gene` | `array` | 100% | `[{"_id": "RDBECOLIGNC01250", "locusTag": "b0001", "name": "thrL"}, ...` |
| `organisms` | `object` | 100% | `{}` |
| `rank` | `double` | 100% | `0.0` |
| `rgbColor` | `string` | 100% | `"5, 241, 59"` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `gene` | `_id`, `locusTag`, `name` |

## Example (first document, simplified)

```json
{
  "_id": "6a8ca26f7d4712e7e5f398e5",
  "gene": [
    {
      "_id": "RDBECOLIGNC01250",
      "locusTag": "b0001",
      "name": "thrL"
    },
    {
      "_id": "RDBECOLIGNC01250",
      "locusTag": "b0001",
      "name": "thrL"
    }
  ],
  "organisms": {},
  "rank": 0.0,
  "rgbColor": "5, 241, 59"
}
```

## Indexes

| Name | Keys |
|---|---|
| `gene_name_1` | `{"gene.name": {"$numberInt": "1"}}` |
| `gene_id_1` | `{"gene.id": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
