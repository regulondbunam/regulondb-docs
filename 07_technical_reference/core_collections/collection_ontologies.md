# Collection: Ontologies (`ontologies`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 1

## Purpose

Stores ontology roots/metadata used by ontology-linked terms.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 1 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBONTOLGON00001"` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `citations` | `array<string>` |  | 0% |  |  |
| `createdBy` | `array<string>` |  | 0% |  |  |
| `description` | `string` |  | 100% |  | `"Class Gene-Ontology-Terms is the root of the Gene Ontology (GO).  ...` |
| `externalCrossReferences` | `array<object>` |  | 0% |  |  |
| `iri` | `string` |  | 0% |  |  |
| `name` | `string` | yes | 100% |  | `"Gene Ontology Terms"` |
| `note` | `string` |  | 0% |  |  |
| `ontologyCode` | `string` |  | 0% |  |  |
| `versionIri` | `string` |  | 0% |  |  |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBONTOLGON00001",
  "description": "Class Gene-Ontology-Terms is the root of the Gene Ontology (GO).  In a PGDB,\ngene products (including monomers, multimer...",
  "name": "Gene Ontology Terms"
}
```

## Main Relationships

- `terms.ontologies_id` -> ontologies collection

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
