<img src="../../assets/icons/technical.svg" alt="" width="48">

# Datamart: HT Metadata (`metadata`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 12
- **Size of the BSON file:** 22.1 KB

## Purpose

General metadata and release information of the HT collections by dataset type.

## Used By

High Throughput pages.

## Source (core collections)

HT dataset curation. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 12 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"METADATA_GSELEX_RNAP_BINDING_SITES_RNAP_BINDING_SITES"` |
| `datasetType` | `string` | 100% | `"RNAP_BINDING_SITES"` |
| `reference` | `array` | 92% | `[28666008, 34787538, "..."]` |
| `releaseDate` | `string` | 100% | `"19/02/2026"` |
| `source` | `string` | 100% | `"RNAP_BINDING_SITES"` |
| `status` | `string` | 100% | `"CURRENT"` |
| `metadataContent` | `string` | 42% | |

## Example (first document, simplified)

```json
{
  "_id": "METADATA_GSELEX_RNAP_BINDING_SITES_RNAP_BINDING_SITES",
  "datasetType": "RNAP_BINDING_SITES",
  "reference": [
    28666008,
    34787538,
    "..."
  ],
  "releaseDate": "19/02/2026",
  "source": "RNAP_BINDING_SITES",
  "status": "CURRENT"
}
```

## Related Content
- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
