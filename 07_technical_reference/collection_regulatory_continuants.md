# Collection: Regulatory Continuants

## Purpose

Stores regulatory continuants (for example metabolites and small molecules) linked to regulation context.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable continuant identifier | `string` | `RDBECOLICNC00001` |
| `name` | Continuant name | `string` | `(<i>S</i>)-2-acetolactate` |
| `type` | Continuant type/class | `string` | `metabolite` |
| `synonyms` | Alternative names | `array<string>` | `["alpha-acetolactate"]` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `externalCrossReferences` | External mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00024","objectId":"C06010"}]` |
| `internalComment` | Internal provenance comment | `string` | `; Source: EcoCyc` |

## Example (simplified)

```json
{
  "_id": "RDBECOLICNC00001",
  "name": "(S)-2-acetolactate",
  "type": "metabolite",
  "organisms_id": "RDBECOLIORC00001"
}
```

## Main Relationships

- `organisms_id` -> organisms collection
- `externalCrossReferences[].externalCrossReferences_id` -> external cross-reference catalog

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
