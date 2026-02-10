# Collection: Products

## Purpose

Stores gene products (proteins and other functional products), including biochemical attributes and cross-references.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable product identifier | `string` | `RDBECOLIPDC00001` |
| `name` | Product full name | `string` | `1-acyl-sn-glycerol-3-phosphate acyltransferase` |
| `abbreviatedName` | Short product name | `string` | `PlsC` |
| `genes_id` | Linked gene identifier | `string` | `RDBECOLIGNC03006` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `sequence` | Product sequence | `string` | `MNNR...` |
| `molecularWeight` | Molecular weight value | `number` | `28193.0` |
| `molecularWeightsKd` | Molecular weight in kDa | `number` | `28.193` |
| `locations` | Cellular localization entries | `array<object>` | `[{"name":"cytosol"}]` |
| `terms` | Ontology/term associations | `array<object>` | `[{"terms_id":"RDBONTOLGON02409"}]` |
| `citations` | Supporting publication/evidence links | `array<object>` | `[{"publications_id":"RDBECOLIPRC06087"}]` |
| `externalCrossReferences` | External mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00059","objectId":"P26647"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIPDC00001",
  "abbreviatedName": "PlsC",
  "genes_id": "RDBECOLIGNC03006",
  "organisms_id": "RDBECOLIORC00001"
}
```

## Main Relationships

- `genes_id` -> genes collection
- `terms[].terms_id` -> terms collection
- `citations[].publications_id` -> publications collection

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
