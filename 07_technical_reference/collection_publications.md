# Collection: Publications

## Purpose

Stores publication records referenced by citations across curated objects.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable publication identifier | `string` | `RDBECOLIPRC00001` |
| `externalCrossReferences` | External publication mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00013","objectId":"PUB-0010525738"}]` |
| `internalComment` | Internal provenance comment | `string` | `; Source: EcoCyc` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIPRC00001",
  "externalCrossReferences": [
    { "externalCrossReferences_id": "RDBECOLIERC00013", "objectId": "PUB-0010525738" }
  ]
}
```

## Main Relationships

- Referenced via `citations[].publications_id` in multiple collections.

## Notes

- Detailed bibliographic metadata may be resolved through linked external references.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
