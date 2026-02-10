# Collection: Genes

## Purpose

Stores core gene objects with genomic coordinates, sequence, and cross-references.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable internal gene identifier | `string` | `RDBECOLIGNC00001` |
| `name` | Preferred gene symbol/name | `string` | `alr` |
| `synonyms` | Alternative names and aliases | `array<string>` | `["alr5", "EG10001"]` |
| `bnumber` | E. coli b-number identifier | `string` | `b4053` |
| `leftEndPosition` | Genomic start coordinate | `integer` | `4265782` |
| `rightEndPosition` | Genomic end coordinate | `integer` | `4266861` |
| `strand` | DNA strand orientation | `string` | `forward` |
| `sequence` | Nucleotide sequence | `string` | `ATGCAAGCG...` |
| `gcContent` | GC percentage/value for the sequence | `number` | `55.92` |
| `centisomePosition` | Genomic position in centisomes | `number` | `91.90224` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `externalCrossReferences` | External database links | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00063","objectId":"ECK4045+b4053"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIGNC00001",
  "name": "alr",
  "bnumber": "b4053",
  "leftEndPosition": 4265782,
  "rightEndPosition": 4266861,
  "strand": "forward",
  "organisms_id": "RDBECOLIORC00001"
}
```

## Main Relationships

- `organisms_id` -> organisms collection
- `externalCrossReferences[].externalCrossReferences_id` -> external cross-reference catalog

## Notes

- `synonyms` may include historical names and external aliases.
- Coordinates and strand support direct genomic mapping workflows.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
