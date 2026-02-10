# Database Dumps and Full Exports

This guide explains when and how to work with full RegulonDB exports for local analysis and reproducible pipelines.

## Purpose

Database dumps are useful when you need:

- Offline analysis
- Bulk integration into local workflows
- Reproducible snapshots tied to a specific release period

## Main Access Points

- Downloadable datasets portal: [https://regulondb.ccg.unam.mx/datasets](https://regulondb.ccg.unam.mx/datasets)
- Datamarts/API docs: [https://regulondb.ccg.unam.mx/doc_datamarts](https://regulondb.ccg.unam.mx/doc_datamarts)
- Docker reference: [https://regulondb.ccg.unam.mx/manual/apiSoftware/docker](https://regulondb.ccg.unam.mx/manual/apiSoftware/docker)

## What Is Covered by Dumps/Exports

Depending on release and distribution method, exports may include:

- Core biological objects (genes, operons, promoters, regulators, regulons)
- Regulatory interactions and associated evidence
- Supporting metadata and cross-references

## Recommended Workflow

1. Identify whether you need table-level datasets or full local deployment data.
2. Download the relevant files from the datasets portal.
3. Document release context (date, source URL, version notes).
4. Load the data into your local analysis stack (for example, MongoDB-based pipelines).
5. Cross-check with release notes for schema or content updates.

## Related Pages

- [Dataset Downloads](dataset_downloads.md)
- [API Access](api_access.md)
- [Docker Installation Guide](technical_resources/docker_installation.md)
- [Version History](../05_releases_updates/version_history.md)
- [Release Notes](../05_releases_updates/release_notes.md)

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
