<img src="../assets/icons/data_access.svg" alt="" width="48">

# Database Dumps and Full Exports

This guide explains how to obtain complete copies of RegulonDB, by release, for local analysis and reproducible pipelines.

## Purpose

Full exports are useful when you need:

- Offline analysis.
- Bulk integration into local workflows.
- Reproducible snapshots tied to a specific RegulonDB release.

## Options

| Option | What you get | Where |
|:-------|:-------------|:------|
| **Release download (zip)** | A MongoDB dump of the release (`mongodump` format: `.bson` and `.metadata.json` files) with two databases, `regulondbdatamarts` and `regulondbht`. These are the datamarts read by the web interface and the API, generated from the core collections. Restore it with `mongorestore` (see the [MongoDB Local Installation Guide](technical_resources/mongodb_installation.md)). | **Releases & Downloads** in the main navigation: open the release note of the version you need and click **DOWNLOAD**. |
| **Local instance with Docker** | The complete database (MongoDB), the web application, and the GraphQL API running on your computer. | [Docker Installation Guide](../07_technical_reference/rdb_docker_instance.md) |
| **Individual datasets** | Specific files (for example, `TF-RISet`, `GeneProductSet`), complete or filtered. | [Dataset Downloads](dataset_downloads.md) |
| **Persistent identifier (DOI)** | A citable record of the release in Zenodo, when available (for example, RegulonDB v12.0.0: [doi:10.5281/zenodo.8346680](https://doi.org/10.5281/zenodo.8346680)). | [Zenodo](https://zenodo.org/records/8346680) |

## Available Releases

The list of releases, with their dates, release notes, and download links, is available on the [RegulonDB release history](https://regulondb.ccg.unam.mx/summaryHistory). Each release note states the EcoCyc version used for gene and product annotation and the object counts of that release.

## Recommended Workflow

1. Decide whether you need individual datasets, the full release download, or a local deployment.
2. Download the files of the release you need from **Releases & Downloads**.
3. Record the release number, release date, and download date.
4. Load the data into your local analysis environment (for example, with the [MongoDB Local Installation Guide](technical_resources/mongodb_installation.md) or a Docker instance).
5. Read the release note for schema or content changes before updating an existing pipeline.

## Related Content
- [Dataset Downloads](dataset_downloads.md)
- [API Access (GraphQL)](api_access.md)
- [Docker Installation Guide](../07_technical_reference/rdb_docker_instance.md)
- [Version History](../05_releases_updates/version_history.md)
- [Release Notes](../05_releases_updates/release_notes.md)
- [How to Cite RegulonDB](../00_about_policies/how_to_cite.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
