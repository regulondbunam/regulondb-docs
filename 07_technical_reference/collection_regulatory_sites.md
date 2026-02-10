# Collection: Regulatory Sites

## Purpose

Stores regulatory binding sites with genomic coordinates, sequence, and confidence/citation support.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable regulatory site identifier | `string` | `RDBECOLIBSC00001` |
| `sequence` | Site sequence | `string` | `cacttttgcgCCAATTATGG...` |
| `leftEndPosition` | Site start coordinate | `integer` | `1825765` |
| `rightEndPosition` | Site end coordinate | `integer` | `1825784` |
| `absolutePosition` | Absolute central/derived position | `number` | `1825774.5` |
| `length` | Site length | `integer` | `20` |
| `regulationType` | Regulation type context | `string` | `Transcription` |
| `confidenceLevel` | Confidence label | `string` | `S` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `citations` | Supporting evidence/publication links | `array<object>` | `[{"evidences_id":"RDBECOLIEVC00017"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIBSC00001",
  "leftEndPosition": 1825765,
  "rightEndPosition": 1825784,
  "confidenceLevel": "S"
}
```

## Main Relationships

- Referenced by `regulatoryInteractions.regulatorySites_id`
- `citations[].evidences_id` -> evidences collection
- `citations[].publications_id` -> publications collection

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
