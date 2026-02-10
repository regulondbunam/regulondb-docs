# MongoDB Local Installation Guide

This guide explains how to prepare a local MongoDB environment for working with RegulonDB data exports.

## Purpose

To support local exploration, reproducible analysis, and development workflows that require direct access to structured collections.

## Prerequisites

- MongoDB Community Edition or compatible MongoDB service.
- Terminal access.
- Local storage for data files and indexes.
- RegulonDB export files from official channels.

## Data Sources

- Dataset portal: [https://regulondb.ccg.unam.mx/datasets](https://regulondb.ccg.unam.mx/datasets)
- Datamarts docs: [https://regulondb.ccg.unam.mx/doc_datamarts](https://regulondb.ccg.unam.mx/doc_datamarts)

## General Workflow

1. Install and start MongoDB locally.
2. Create a dedicated database name for your RegulonDB snapshot.
3. Download export files (JSON/related resources).
4. Import collections using your preferred MongoDB import method.
5. Validate imported collection names and record counts.

## Validation Checklist

- Target database is accessible.
- Expected collections are present.
- Basic sample queries return documents.
- Imported snapshot date and source are documented.

## Good Practices

- Keep each imported snapshot versioned by date or release label.
- Avoid mixing data from different release windows in one database.
- Store import scripts/commands in your project notes for reproducibility.
- Reimport after major schema changes indicated in release notes.

## Related Pages

- [Database Dumps](../database_dumps.md)
- [Web Services Usage Guide](web_services_usage.md)
- [Database Collections Structure](database_collections/README.md)

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
