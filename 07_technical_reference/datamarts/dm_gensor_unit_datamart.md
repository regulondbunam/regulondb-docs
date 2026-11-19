# Datamart: GENSOR Unit (`gensorUnitDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 240
- **Size of the BSON file:** 12.0 MB

## Purpose

One document per GENSOR Unit (genetic sensory response unit): the unit description and its reactions, with the total number of components and reactions.

## Used By

GraphQL `getAllGUs`, `getGUsBy`; GENSOR Unit pages and catalog.

## Source (core collections)

GENSOR Unit curation and core collections. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 240 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLITFC00172"` |
| `gensorUnit` | `object` | 100% | `{"_id": "RDBECOLITFC00172", "components": [{"name": "DicA", "type":...` |
| `reactions` | `array` | 100% | `[{"components": [{"function": "activator", "name": "DicA", "type": ...` |
| `totalOfComponents` | `int` | 100% | `12` |
| `totalOfReactions` | `int` | 100% | `9` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `gensorUnit` | `_id`, `components`, `geneOntology`, `groups`, `name`, `signalName`, `summary` |
| `reactions` | `components`, `description`, `name`, `number`, `order`, `pathwayComponents`, `type` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLITFC00172",
  "gensorUnit": {
    "_id": "RDBECOLITFC00172",
    "components": [
      {
        "name": "DicA",
        "type": "transcription_factor"
      },
      {
        "name": "DicB",
        "type": "protein"
      },
      "..."
    ],
    "geneOntology": {
      "biologicalProcess": [
        {
          "_id": "RDBONTOLGON03225",
          "genes": [
            "dicC",
            "dicB"
          ],
          "name": "GO:0051301 - cell division"
        },
        {
          "_id": "RDBONTOLGON02997",
          "genes": [
            "dicC"
          ],
          "name": "GO:0006355 - regulation of DNA-templated transcription"
        },
        "..."
      ],
      "cellularComponent": [
        {
          "_id": "RDBONTOLGON02489",
          "genes": [
            "intQ",
            "insD7",
            "..."
          ],
          "name": "GO:0005829 - cytosol"
        },
        {
          "_id": "RDBONTOLGON03826",
          "genes": [
            "ydfD"
          ],
          "name": "GO:0016020 - membrane"
        }
      ],
      "molecularFunction": [
        {
          "_id": "RDBONTOLGON02650",
          "genes": [
            "dicC"
          ],
          "name": "GO:0003677 - DNA binding"
        },
  ...
```

## Indexes

| Name | Keys |
|---|---|
| `gensorUnit_name_1` | `{"gensorUnit.name": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
