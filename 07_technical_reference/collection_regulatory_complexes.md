# Collection: Regulatory Complexes

## Purpose

Stores regulatory or functional complexes composed of products, including stoichiometry and contextual notes.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable complex identifier | `string` | `RDBECOLIRCC00001` |
| `type` | Complex state/type label | `string` | `active` |
| `products` | Components and coefficients | `array<object>` | `[{"products_id":"RDBECOLIPDC00223","coefficient":2}]` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `note` | Biological note/description | `string` | `Acetyl-CoA carboxyltransferase...` |
| `externalCrossReferences` | External mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00013","objectId":"ACETYL-COA-CARBOXYLTRANSFER-CPLX"}]` |
| `internalComment` | Internal provenance comment | `string` | `; Source: EcoCyc` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIRCC00001",
  "type": "active",
  "organisms_id": "RDBECOLIORC00001"
}
```

## Main Relationships

- `products[].products_id` -> products collection
- `organisms_id` -> organisms collection

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
