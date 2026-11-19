# Collection: Regulators (`regulators`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 293

## Purpose

Defines regulator entities (including transcription factors), with confidence, conformations, and evidence-linked citations.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 293 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLITFC00001"` |
| `abbreviatedName` | `string` |  | 100% |  | `"YafC"` |
| `citations` | `array<object>` |  | 98% |  | `[{"evidences_id": "RDBECOLIEVC00056", "publications_id": "RDBECOLIP...` |
| `confidenceLevel` | `string` |  | 0% |  |  |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00004", "objectId": "P3...` |
| `name` | `string` |  | 100% |  | `"DNA-binding transcriptional regulator YafC"` |
| `synonyms` | `array<string>` |  | 100% |  | `["YafC", "predicted DNA-binding transcriptional regulator LYSR-type"]` |
| `type` | `string` | yes | 100% | values: `small RNA`, `transcriptionFactor`, `regulatoryContinuant` | `"transcriptionFactor"` |
| `regulatorClass` | `array<string>` |  | 100% |  | `["\|Polypeptides\|"]` |
| `regulationType` | `string` |  | 100% |  | `"Transcription-Factor-Binding"` |
| `note` | `string` |  | 70% |  | `"YafC, which contains a helix-turn-helix motif to bind DNA in its N...` |
| `conformations` | `array<object>` |  | 100% |  | `[{"_id": "RDBECOLIPDC01127", "type": "product", "class": "active"}]` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `conformations` | `_id`, `type`, `class` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLITFC00001",
  "name": "DNA-binding transcriptional regulator YafC",
  "abbreviatedName": "YafC",
  "citations": [
    {
      "evidences_id": "RDBECOLIEVC00056",
      "publications_id": "RDBECOLIPRC03267"
    },
    {
      "evidences_id": "RDBECOLIEVC00058",
      "publications_id": "RDBECOLIPRC10840"
    }
  ],
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00004",
      "objectId": "P30864"
    },
    {
      "externalCrossReferences_id": "RDBECOLIERC00025",
      "objectId": "IPR005119"
    },
    "..."
  ],
  "type": "transcriptionFactor",
  "synonyms": [
    "YafC",
    "predicted DNA-binding transcriptional regulator LYSR-type"
  ],
  "regulatorClass": [
    "|Polypeptides|"
  ],
  "regulationType": "Transcription-Factor-Binding",
  "conformations": [
    {
      "_id": "RDBECOLIPDC01127",
      "type": "product",
      "class": "active"
    }
  ],
  "note": "YafC, which contains a helix-turn-helix motif to bind DNA in its N-terminal domain, appears to belong to the LysR family..."
}
```

## Main Relationships

- `conformations[]._id` -> regulatory complex or product objects
- `citations[].evidences_id` -> evidences collection
- `citations[].publications_id` -> publications collection

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
