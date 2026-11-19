# Collection: External Cross References (`externalCrossReferences`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 57

## Purpose

Defines external resource descriptors used by many collections for interoperable cross-links.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 57 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIERC00001"` |
| `description` | `string` |  | 98% |  | `"Protein Data Bank"` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `name` | `string` |  | 100% |  | `"PDB"` |
| `note` | `string` |  | 75% |  | `"The PDB archive contains information about experimentally-determin...` |
| `url` | `string` |  | 100% |  | `"http://www.rcsb.org/structure/~A"` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIERC00001",
  "description": "Protein Data Bank",
  "internalComment": "; Source: EcoCyc",
  "name": "PDB",
  "note": "The PDB archive contains information about experimentally-determined structures of proteins, nucleic acids, and complex ...",
  "url": "http://www.rcsb.org/structure/~A"
}
```

## Main Relationships

- Referenced as `externalCrossReferences_id` from multiple collections.

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
