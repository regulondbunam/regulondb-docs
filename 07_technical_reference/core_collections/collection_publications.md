# Collection: Publications (`publications`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 32,475

## Purpose

Stores publication records referenced by citations across curated objects.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 32,475 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIPRC00001"` |
| `authors` | `array<string>` |  | 100% |  | `["Bravo J", "Mate MJ", "Schneider T", "Switala J", "Wilson K", "Loe...` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "PU...` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `note` | `string` |  | 0% |  |  |
| `pmid` | `string` |  | 100% |  | `"10022351"` |
| `source` | `string` |  | 100% |  | `"Proteins 34(2);155-66"` |
| `title` | `string` |  | 100% |  | `"Structure of catalase HPII from Escherichia coli at 1.9 A resoluti...` |
| `url` | `string` |  | 0% |  | `"https://journals.asm.org/doi/10.1128/jb.183.4.1499-1503.2001"` |
| `year` | `number` |  | 100% |  | `1999` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIPRC00001",
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "PUB-0010525738"
    }
  ],
  "internalComment": "; Source: EcoCyc"
}
```

## Main Relationships

- Referenced via `citations[].publications_id` in multiple collections.

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
