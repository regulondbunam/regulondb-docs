<img src="../../assets/icons/data_access.svg" alt="" width="48">

# MongoDB Local Installation Guide

This guide explains how to restore a RegulonDB release in a local MongoDB server, so you can query its collections directly.

## Purpose

To support local exploration, reproducible analysis, and development workflows that require direct access to the RegulonDB collections of a specific release.

## Prerequisites

- MongoDB Community Server (or a compatible MongoDB service), running locally.
- [MongoDB Database Tools](https://www.mongodb.com/docs/database-tools/), which include `mongorestore`.
- The MongoDB shell (`mongosh`), to check the restored data.
- The release download (zip) from **Releases & Downloads** (see [Database Dumps](../database_dumps.md)).

## What the Release Download Contains

The zip file is a MongoDB dump (created with `mongodump`). It contains one folder per database, and one pair of files per collection:

- `<collection>.bson`: the documents of the collection.
- `<collection>.metadata.json`: the collection indexes and options.

| Database folder | Content | Example collections |
|:----------------|:--------|:--------------------|
| `regulondbdatamarts` | Datamarts used by the web application and the GraphQL API. | `geneDatamart`, `operonDatamart`, `regulonDatamart`, `sigmulonDatamart`, `gensorUnitDatamart`, `srnaDatamart`, `regulatoryNetworkDatamart`, `evidencesDatamart`, `dnaFeatures`, `geneCoexpressions`, `growthCondition`, `mcoTree`, `phrases`, `overviews`, `downloadableFilesDatamart`, `databaseInfo` |
| `regulondbht` | High-throughput (HT) datasets and their metadata. | `dataset`, `authorsData`, and other HT collections |

> **Datamarts and core collections.** The release dump contains the **datamarts**: view-like collections aligned with the web interface, which the web application and the GraphQL API read from. They are generated from the RegulonDB **core collections** (one collection per biological object), described in the [Technical Reference](../../07_technical_reference/database_schema_overview.md). Each datamart collection is documented in [Datamarts (Release Dump)](../../07_technical_reference/datamarts/README.md).

## Restore Steps

1. Unzip the release download. In this example, the dump is extracted to a folder named `regulondb_dump/` that contains `regulondbdatamarts/` and `regulondbht/`.

2. Restore all databases in the dump:

```bash
mongorestore --dir regulondb_dump/
```

   To restore only one database, use `--nsInclude`:

```bash
mongorestore --dir regulondb_dump/ --nsInclude "regulondbdatamarts.*"
```

   To replace a previous release already loaded in the same server, add `--drop` (this deletes the existing collections before restoring them):

```bash
mongorestore --drop --dir regulondb_dump/
```

3. Check that the databases and collections are present:

```bash
mongosh regulondbdatamarts --eval "db.getCollectionNames()"
```

4. Check the restored release:

```bash
mongosh regulondbdatamarts --eval "db.databaseInfo.find().limit(1)"
```

## Validation Checklist

- Both databases (`regulondbdatamarts` and `regulondbht`) are listed by `show dbs`.
- The expected collections are present.
- Sample queries return documents.
- The release number and download date are recorded in your project notes.

## Good Practices

- Keep one MongoDB instance (or database name) per release, and do not mix data from different releases.
- Store the restore commands in your project notes for reproducibility.
- Read the release note before replacing a release in an existing pipeline, since collection structures can change.
- If you also need the web application and the GraphQL API, use the [Docker Installation Guide](../../07_technical_reference/rdb_docker_instance.md) instead.

## Related Content
- [Database Dumps](../database_dumps.md)
- [API Access (GraphQL)](../api_access.md)
- [Core Database Collections (Technical Reference)](../../07_technical_reference/core_collections/README.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
