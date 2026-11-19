<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Evidences (`evidences`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 115

## Purpose

Defines evidence vocabulary used to support curation confidence and provenance across RegulonDB objects.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 115 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIEVC00034"` |
| `code` | `string` |  | 100% |  | `"COMP-AINF-SIMILAR-TO-CONSENSUS"` |
| `externalCrossReferences` | `array<object>` |  | 83% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "EV...` |
| `head` | `string` |  | 57% |  | `"RDBECOLIEVC00039"` |
| `internalComment` | `string` |  | 83% |  | `"; Source: EcoCyc"` |
| `name` | `string` | yes | 100% |  | `"Automated inference based on similarity to consensus sequences"` |
| `note` | `string` |  | 98% |  | `"A DNA sequence similar to previously known consensus sequences is ...` |
| `pertainsTo` | `array<string>` |  | 81% |  | `["mRNA-Binding-Sites", "DNA-Binding-Sites"]` |
| `type` | `string` |  | 77% |  | `"W"` |
| `crossEvidenceCodeRule` | `number` |  | 41% |  | `7` |
| `evidenceClass` | `string` |  | 0% |  |  |
| `evidenceCategory` | `string` |  | 77% |  | `"non-experimental"` |
| `evidenceApproach` | `string` |  | 43% |  | `"non-experimental"` |
| `noteWeb` | `string` |  | 64% |  | `"A DNA sequence similar to previously known consensus sequences is ...` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIEVC00034",
  "code": "COMP-AINF-SIMILAR-TO-CONSENSUS",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "EV-COMP-AINF-SIMILAR-TO-CONSENSUS"
    }
  ],
  "internalComment": "; Source: EcoCyc",
  "name": "Automated inference based on similarity to consensus sequences",
  "note": "A DNA sequence similar to previously known consensus sequences is computationally identified.",
  "pertainsTo": [
    "mRNA-Binding-Sites",
    "DNA-Binding-Sites"
  ],
  "crossEvidenceCodeRule": 7,
  "evidenceApproach": "non-experimental",
  "evidenceCategory": "non-experimental",
  "head": "RDBECOLIEVC00039",
  "noteWeb": "A DNA sequence similar to previously known consensus sequences is computationally identified."
}
```

## Main Relationships

- Referenced from `citations[].evidences_id` in multiple collections.
- `externalCrossReferences[].externalCrossReferences_id` -> external cross-reference catalog.

## Related Content
- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
