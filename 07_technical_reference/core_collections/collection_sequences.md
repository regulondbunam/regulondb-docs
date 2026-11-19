<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Sequences (`sequences`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 27

## Purpose

Stores the counters used to generate RegulonDB identifiers: one document per object type (for example, `genes`, `promoters`, `operons`), with the organism, class and subclass acronyms that form the identifier prefix and the last value assigned.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 27 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `object` |  | 100% |  | `{"$oid": "6997ce2fa314f8d9e6645ced"}` |
| `classAcronym` | `string` |  | 100% |  | `"ECOLI"` |
| `database` | `string` |  | 100% |  | `"regulondbmultigenomic"` |
| `organism` | `string` |  | 93% |  | `"ECOLI"` |
| `subclassAcronym` | `string` |  | 100% |  | `"ORG"` |
| `type` | `string` |  | 100% |  | `"organisms"` |
| `value` | `integer` |  | 100% |  | `2` |
| `ontologyName` | `string` |  | 7% |  | `"geneOntology"` |

## Example (first document, simplified)

```json
{
  "_id": {
    "$oid": "6997ce2fa314f8d9e6645ced"
  },
  "classAcronym": "ECOLI",
  "database": "regulondbmultigenomic",
  "organism": "ECOLI",
  "subclassAcronym": "ORG",
  "type": "organisms",
  "value": 2
}
```

## Related Content
- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
