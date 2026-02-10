# Collection: Regulators

## Purpose

Defines regulator entities (including transcription factors), with confidence, conformations, and evidence-linked citations.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable internal regulator identifier | `string` | `RDBECOLITFC00001` |
| `name` | Full regulator name/description | `string` | `DNA-binding transcriptional repressor ExuR` |
| `abbreviatedName` | Short regulator symbol | `string` | `ExuR` |
| `type` | Regulator object type | `string` | `transcriptionFactor` |
| `synonyms` | Alternative names in literature | `array<string>` | `["ExuR", "negative regulator of exu regulon"]` |
| `regulatorClass` | Regulator classification tag(s) | `array<string>` | `["|Polypeptides|"]` |
| `regulationType` | Regulatory mechanism type | `string` | `Transcription-Factor-Binding` |
| `confidenceLevel` | Confidence label for annotation | `string` | `W` |
| `conformations` | Active/inactive conformation entries | `array<object>` | `[{"_id":"RDBECOLIRCC00106","class":"active"}]` |
| `citations` | Supporting evidence/publication links | `array<object>` | `[{"evidences_id":"RDBECOLIEVC00023"}]` |
| `externalCrossReferences` | External database mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00059","objectId":"P0ACL2"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLITFC00001",
  "abbreviatedName": "ExuR",
  "type": "transcriptionFactor",
  "confidenceLevel": "W",
  "regulationType": "Transcription-Factor-Binding"
}
```

## Main Relationships

- `conformations[]._id` -> regulatory complex or product objects
- `citations[].evidences_id` -> evidences collection
- `citations[].publications_id` -> publications collection

## Notes

- Regulators can include active/inactive conformations.
- Textual notes may include long biological descriptions with citation tags.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
