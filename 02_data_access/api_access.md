# API Access (GraphQL and Web Services)

This guide describes how to access RegulonDB programmatically through the public API and datamart documentation.

## Entry Points

- API/datamarts documentation: [https://regulondb.ccg.unam.mx/doc_datamarts](https://regulondb.ccg.unam.mx/doc_datamarts)
- API and software portal section: `API & software` in the main web navigation

## API Scope

The API documentation includes query groups and objects such as:

- Gene
- Operon
- Regulon
- Sigmulon
- GENSOR Unit
- All Data / DB Info / DownloadableFile / GrowthConditions / HT Dataset

Typical query families include:

- `getAll...` style list queries
- `get...By` style filtered search queries
- utility queries for object properties and associated phrases

## Recommended Query Workflow

1. Open the datamarts documentation page.
2. Select the biological object of interest in the left menu.
3. Review the available queries and descriptions.
4. Start with broad `getAll...` queries to inspect structure.
5. Switch to `get...By` queries for targeted retrieval.

## Good Practices

- Prefer targeted queries for large objects to reduce payload size.
- Keep track of query date and endpoint used for reproducibility.
- Validate field names against current API docs before automation.

## Related Pages

- [Web Services Usage Guide](technical_resources/web_services_usage.md)
- [Dataset Downloads](dataset_downloads.md)
- [Database Dumps](database_dumps.md)

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
