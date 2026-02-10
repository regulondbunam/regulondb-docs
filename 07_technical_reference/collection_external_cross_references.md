# Collection: External Cross References

## Purpose

Defines external resource descriptors used by many collections for interoperable cross-links.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable cross-reference identifier | `string` | `RDBECOLIERC00037` |
| `name` | Source short name | `string` | `PDB` |
| `description` | Source description | `string` | `Protein Data Bank` |
| `url` | URL template (often with placeholder) | `string` | `http://www.rcsb.org/structure/~A` |
| `note` | Additional source notes | `string` | `The PDB archive contains information...` |
| `internalComment` | Internal provenance comment | `string` | `; Source: EcoCyc` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIERC00037",
  "name": "PDB",
  "description": "Protein Data Bank",
  "url": "http://www.rcsb.org/structure/~A"
}
```

## Main Relationships

- Referenced as `externalCrossReferences_id` from multiple collections.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
