# Web Services Usage Guide

This guide describes how to use RegulonDB web services for programmatic data retrieval.

## Entry Point

- API/datamarts documentation: [https://regulondb.ccg.unam.mx/doc_datamarts](https://regulondb.ccg.unam.mx/doc_datamarts)

## Scope

RegulonDB web services expose queryable biological objects, including:

- Gene
- Operon
- Regulon
- Sigmulon
- GENSOR Unit
- Additional supporting objects and metadata

## Typical Query Types

In the API documentation, you will commonly find:

- `getAll...` queries to list records in a collection.
- `get...By` queries to retrieve records using search criteria.
- Object-level utility queries for associated properties.

## Recommended Workflow

1. Open the documentation page.
2. Select the object type you need in the left menu.
3. Read query descriptions and expected return fields.
4. Start with a small query to validate structure.
5. Move to filtered queries for production usage.

## Practical Recommendations

- Keep local logs of query date and source.
- Prefer filtered queries for large datasets.
- Validate output structure when release notes indicate updates.
- Use downloaded snapshots for heavy offline processing.

## Related Pages

- [API Access](../api_access.md)
- [Dataset Downloads](../dataset_downloads.md)
- [Version History](../../05_releases_updates/version_history.md)

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
