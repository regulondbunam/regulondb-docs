# Collection: Terms

## Purpose

Stores ontology terms and their membership links to biological objects.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable term identifier | `string` | `RDBONTOLGON02409` |
| `name` | Term name | `string` | `DNA/RNA hybrid annealing activity` |
| `definition` | Term definition and source | `object` | `{"source":"EcoCyc","text":"An activity that..."}` |
| `ontologies_id` | Linked ontology identifier | `string` | `RDBONTOLGON00001` |
| `subClassOf` | Parent term references | `array<string>` | `["RDBONTOLGON02432"]` |
| `members` | Associated object memberships | `object` | `{"products":["RDBECOLIPDC01626"]}` |
| `externalCrossReferences` | External ontology mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00013","objectId":"GO:0097098"}]` |

## Example (simplified)

```json
{
  "_id": "RDBONTOLGON02409",
  "name": "DNA/RNA hybrid annealing activity",
  "ontologies_id": "RDBONTOLGON00001"
}
```

## Main Relationships

- `ontologies_id` -> ontologies collection
- `members` links to products and potentially other object types.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
