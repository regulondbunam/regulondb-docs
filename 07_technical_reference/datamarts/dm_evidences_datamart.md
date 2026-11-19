# Datamart: Evidences (`evidencesDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 115
- **Size of the BSON file:** 55.1 KB

## Purpose

Evidence catalog used in the interface (evidence codes, names, types, and categories).

## Used By

Evidence labels on object pages; `EvidenceSet` dataset.

## Source (core collections)

Core collection `evidences` and the local evidence catalog. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 115 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLIEVC00001"` |
| `category` | `string` | 77% | `"Classical experiment"` |
| `code` | `string` | 100% | `"EXP-IGI-FUNC-COMPLEMENTATION"` |
| `name` | `string` | 100% | `"Inferred by functional complementation"` |
| `note` | `string` | 98% | `"Protein activity inferred by isolating its gene and performing fun...` |
| `pertainsTo` | `array` | 73% | `["Transcription Factors", "Regulators"]` |
| `type` | `string` | 77% | `"S"` |
| `codeRule` | `int` | 41% | |
| `superClassOf` | `array` | 14% | |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIEVC00001",
  "category": "Classical experiment",
  "code": "EXP-IGI-FUNC-COMPLEMENTATION",
  "name": "Inferred by functional complementation",
  "note": "Protein activity inferred by isolating its gene and performing functional complementation of a well characterized heterologous mutant for the protein.",
  "pertainsTo": [
    "Transcription Factors",
    "Regulators"
  ],
  "type": "S"
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
