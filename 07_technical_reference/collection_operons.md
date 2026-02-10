# Collection: Operons

## Purpose

Stores operon objects with genomic range and strand orientation.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable operon identifier | `string` | `RDBECOLIOPC01028` |
| `name` | Operon name | `string` | `yihD` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `strand` | Operon strand orientation | `string` | `forward` |
| `regulationPositions.leftEndPosition` | Operon start coordinate | `integer` | `4042049` |
| `regulationPositions.rightEndPosition` | Operon end coordinate | `integer` | `4042338` |
| `externalCrossReferences` | External links for operon object | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00013","objectId":"TU0-14057"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIOPC01028",
  "name": "yihD",
  "organisms_id": "RDBECOLIORC00001",
  "strand": "forward",
  "regulationPositions": {
    "leftEndPosition": 4042049,
    "rightEndPosition": 4042338
  }
}
```

## Main Relationships

- `organisms_id` -> organisms collection
- `externalCrossReferences[].externalCrossReferences_id` -> external cross-reference catalog

## Notes

- Operon boundaries are used by TU and regulatory reconstruction pipelines.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
