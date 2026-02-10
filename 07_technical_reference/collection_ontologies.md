# Collection: Ontologies

## Purpose

Stores ontology roots/metadata used by ontology-linked terms.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable ontology identifier | `string` | `RDBONTOLGON00001` |
| `name` | Ontology name | `string` | `Gene Ontology Terms` |
| `description` | Ontology description text | `string` | `Class Gene-Ontology-Terms is the root...` |

## Example (simplified)

```json
{
  "_id": "RDBONTOLGON00001",
  "name": "Gene Ontology Terms"
}
```

## Main Relationships

- `terms.ontologies_id` -> ontologies collection

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
