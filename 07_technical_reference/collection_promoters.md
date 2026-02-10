# Collection: Promoters

## Purpose

Stores promoter objects, sigma-factor association, sequence boxes, and transcription start site (TSS) information.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable promoter identifier | `string` | `RDBECOLIPMC00001` |
| `name` | Promoter name | `string` | `spyp` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `strand` | Promoter strand orientation | `string` | `reverse` |
| `sequence` | Promoter sequence | `string` | `acactttc...` |
| `bindsSigmaFactor.sigmaFactors_id` | Linked sigma factor identifier | `string` | `RDBECOLISFC00003` |
| `boxes[]` | Promoter motif boxes (e.g., -10/-35) | `array<object>` | `[{"type":"minus10","sequence":"TAAAGT"}]` |
| `transcriptionStartSite` | TSS coordinates and range | `object` | `{"leftEndPosition":1825688,"range":1}` |
| `distanceToGene` | Distance from promoter to gene context | `integer` | `63` |
| `confidenceLevel` | Confidence label | `string` | `S` |
| `citations` | Supporting evidence/publication links | `array<object>` | `[{"evidences_id":"RDBECOLIEVC00039"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIPMC00001",
  "name": "spyp",
  "strand": "reverse",
  "bindsSigmaFactor": { "sigmaFactors_id": "RDBECOLISFC00003" },
  "transcriptionStartSite": { "leftEndPosition": 1825688, "range": 1 },
  "confidenceLevel": "S"
}
```

## Main Relationships

- `bindsSigmaFactor.sigmaFactors_id` -> sigmaFactors collection
- `citations[].evidences_id` -> evidences collection
- `citations[].publications_id` -> publications collection

## Notes

- `boxes[]` captures promoter motifs (for example minus10, minus35).
- Sequence is represented with strand-aware coordinates.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
