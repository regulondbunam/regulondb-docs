# Datamart: MCO Tree (`mcoTree`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 5,656
- **Size of the BSON file:** 6.1 MB

## Purpose

Terms of the Microbial Condition Ontology (MCO) organized as a tree.

## Used By

GraphQL **ontologyTree** queries; MCO browser.

## Source (core collections)

Core collections `ontologies` and `terms`. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 5,656).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBONTOLGON00002"` |
| `description` | `string` | 100% | `"Catalysis of the reaction: ATP + pantetheine 4'-phosphate = 3'-dep...` |
| `genes` | `array` | 75% | `[{"_id": "RDBECOLIGNC01170", "name": "coaD", "productName": "pantet...` |
| `name` | `string` | 100% | `"pantetheine-phosphate adenylyltransferase activity"` |
| `ontologyId` | `string` | 100% | `"RDBONTOLGON00001"` |
| `subclassOf` | `array` | 100% | `["RDBONTOLGON03240"]` |
| `synonyms` | `array` | 57% | `["ATP:pantetheine-phosphate adenylyltransferase activity", "phospho...` |
| `subclasses` | `array` | 49% | |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `genes` | `_id`, `name`, `productName` |

## Example (first document, simplified)

```json
{
  "_id": "RDBONTOLGON00002",
  "description": "Catalysis of the reaction: ATP + pantetheine 4'-phosphate = 3'-dephospho-CoA + diphosphate.",
  "genes": [
    {
      "_id": "RDBECOLIGNC01170",
      "name": "coaD",
      "productName": "pantetheine-phosphate adenylyltransferase"
    }
  ],
  "name": "pantetheine-phosphate adenylyltransferase activity",
  "ontologyId": "RDBONTOLGON00001",
  "subclassOf": [
    "RDBONTOLGON03240"
  ],
  "synonyms": [
    "ATP:pantetheine-phosphate adenylyltransferase activity",
    "phosphopantetheine adenylyltransferase activity"
  ]
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
