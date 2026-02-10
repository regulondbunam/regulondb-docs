# Collection: Terminators

## Purpose

Stores transcription terminator objects, including class, sequence, and termination-site coordinates.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable terminator identifier | `string` | `RDBECOLITMC00001` |
| `class` | Terminator class/type | `string` | `rho-independent` |
| `sequence` | Terminator sequence | `string` | `agcgtcaaaaGGCC...` |
| `transcriptionTerminationSite` | Termination coordinates | `object` | `{"leftEndPosition":3407286,"rightEndPosition":3407302}` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `citations` | Supporting publication/evidence links | `array<object>` | `[{"publications_id":"RDBECOLIPRC26301"}]` |
| `externalCrossReferences` | External mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00013","objectId":"ACCCT1"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLITMC00001",
  "class": "rho-independent",
  "organisms_id": "RDBECOLIORC00001"
}
```

## Main Relationships

- Referenced by `transcriptionUnits.terminators_ids[]`

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
