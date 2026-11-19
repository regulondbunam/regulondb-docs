# Datamart: Recent Queries (`recentQueriesDM`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 4
- **Size of the BSON file:** 505 B

## Purpose

Recently used queries.

## Used By

GraphQL `getAllUsedQueries`.

## Source (core collections)

Application usage. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 4 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"634626a8caee485685df72ba"` |
| `querySearchString` | `string` | 100% | `"araBAD[gene.name]"` |
| `dateOfUse` | `date` | 100% | `"2022-10-11 00:00:00"` |
| `usedTimes` | `int` | 100% | `1` |
| `__v` | `int` | 100% | `0` |

## Example (first document, simplified)

```json
{
  "_id": "634626a8caee485685df72ba",
  "querySearchString": "araBAD[gene.name]",
  "dateOfUse": "2022-10-11 00:00:00",
  "usedTimes": 1,
  "__v": 0
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
