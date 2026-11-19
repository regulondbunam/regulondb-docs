# Collection: Terms (`terms`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 5,656

## Purpose

Stores ontology terms and their membership links to biological objects.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 5,656 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBONTOLGON04575"` |
| `contributors` | `object` |  | 0% |  |  |
| `definition` | `object` |  | 100% |  | `{"source": "EcoCyc", "text": "The chemical reactions and pathways i...` |
| `description` | `string` |  | 0% |  |  |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "GO...` |
| `hasDbXRef` | `array<string>` |  | 0% |  |  |
| `hasOboNameSpace` | `string` |  | 0% |  |  |
| `hasRelatedSynonyms` | `array<string>` |  | 0% |  |  |
| `internalComment` | `string` |  | 0% |  |  |
| `iri` | `string` |  | 0% |  |  |
| `members` | `object` |  | 75% |  | `{"products": ["RDBECOLIPDC01942", "RDBECOLIPDC04388", "RDBECOLIPDC0...` |
| `name` | `string` | yes | 100% |  | `"glyoxylate metabolic process"` |
| `oboId` | `string` |  | 0% |  |  |
| `ontologies_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBONTOLGON00001"` |
| `subClassOf` | `array<string>` |  | 100% |  | `["RDBONTOLGON01678", "RDBONTOLGON01210"]` |
| `superClassOf` | `array<string>` |  | 49% |  | `["RDBONTOLGON00530", "RDBONTOLGON02250"]` |
| `synonyms` | `array<string>` |  | 57% |  | `["glyoxylate metabolism"]` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `contributors` | `text`, `creationDate` |
| `definition` | `text`, `source` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `members` | `products`, `genes` |

## Example (first document, simplified)

```json
{
  "_id": "RDBONTOLGON04575",
  "definition": {
    "source": "EcoCyc",
    "text": "The chemical reactions and pathways involving glyoxylate, the anion of glyoxylic acid, HOC-COOH."
  },
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "GO:0046487"
    }
  ],
  "members": {
    "products": [
      "RDBECOLIPDC01942",
      "RDBECOLIPDC04388",
      "..."
    ]
  },
  "name": "glyoxylate metabolic process",
  "ontologies_id": "RDBONTOLGON00001",
  "subClassOf": [
    "RDBONTOLGON01678",
    "RDBONTOLGON01210"
  ],
  "superClassOf": [
    "RDBONTOLGON00530",
    "RDBONTOLGON02250"
  ],
  "synonyms": [
    "glyoxylate metabolism"
  ]
}
```

## Main Relationships

- `ontologies_id` -> ontologies collection
- `members` links to products and potentially other object types.

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
