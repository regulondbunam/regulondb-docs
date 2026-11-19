<img src="../assets/icons/data_access.svg" alt="" width="48">

# API Access (GraphQL Web Services)

RegulonDB provides programmatic access to its data through **GraphQL web services**. This guide describes the endpoint, the available queries, and a basic workflow.

## Entry Points

- **GraphQL endpoint:** `https://regulondb.ccg.unam.mx/graphql`
- **Query documentation (datamarts):** [https://regulondb.ccg.unam.mx/doc_datamarts](https://regulondb.ccg.unam.mx/doc_datamarts), also available from **API & software** in the main navigation.
- **Local instance:** if you deploy RegulonDB with Docker, the endpoint is `http://localhost:7000/graphql` (see the [Docker Installation Guide](../07_technical_reference/rdb_docker_instance.md)).

## Example Query

The following query returns the identifier, name, and coordinates of the first five genes:

```graphql
{
  getAllGenes(limit: 5) {
    data {
      gene {
        _id
        name
        leftEndPosition
        rightEndPosition
      }
    }
  }
}
```

You can run it in the browser by opening the endpoint with the query in the URL ([try it](https://regulondb.ccg.unam.mx/graphql?query=%0A%7B%0A%20%20getAllGenes(limit:5)%7B%0A%20%20%20%20data%7B%0A%20%20%20%20%20%20gene%7B%0A%20%20%20%20%20%20%20%20_id%0A%20%20%20%20%20%20%20%20name%0A%20%20%20%20%20%20%20%20leftEndPosition%0A%20%20%20%20%20%20%20%20rightEndPosition%0A%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%20%20%7D%0A%7D%0A)), or from a script by sending an HTTP `POST` request with a JSON body:

```bash
curl -X POST https://regulondb.ccg.unam.mx/graphql \
  -H "Content-Type: application/json" \
  -d '{"query": "{ getAllGenes(limit: 5) { data { gene { _id name leftEndPosition rightEndPosition } } } }"}'
```

## Available Queries

The documentation page groups the queries into three areas.

### Data

| Object | Queries | Description |
|:-------|:--------|:------------|
| Gene | `getAllGenes`, `getGenesBy` | List all genes, or genes matching a search or advancedSearch string. |
| All Data | `getProperties` | List all the properties defined in a collection. |
| Phrases | `getPhraseOf`, `getAllPhrasesInObject` | Phrases of an object by identifier, or all phrases associated with the IDs in an object. |
| Operon | `getAllOperon`, `getOperonBy` | List all operons, or operons matching a search string. |
| Regulon | `getAllRegulon`, `getRegulonBy` | List all regulons, or regulons matching a search string. |
| Sigmulon | `getAllSigmulon`, `getSigmulonBy` | List all sigmulons, or sigmulons matching a search string. |
| Overviews | `getAllObjectInfo`, `getOverview` | List the overview items, or show one overview with all its information. |
| GENSOR Unit | `getAllGUs`, `getGUsBy` | List all GENSOR Units, or units matching a search string. |
| DB Info | `getDatabaseInfo` | Information on all database releases. |
| Recent Queries | `getAllUsedQueries` | List the previously used queries. |
| DownloadableFile | `getDataOfFile`, `listAllFileNames`, `listAllDownloadableFiles` | Data of a downloadable file, list of file names, or all files with their data. |
| GrowthConditions | `getAllGrowthCondition`, `getGrowthConditionBy` | All growth conditions (with optional pagination), or conditions matching search criteria. |
| HT Dataset | `listAllHTSources`, `listAllDatasetTypes`, `listAllDatasetStrategies` | Sources, dataset types, and strategies of RegulonDB high-throughput (HT) data. |

### Tools

Queries that support the RegulonDB tools: **Coexpression**, **DTT** (Drawing Traces Tool), **RegulatoryNetwork**, and **ontologyTree**.

### HT Data

Queries for high-throughput collections: **HT Dataset**, **HT Peaks**, **HT TFBinding**, **HT authorsData**, **HT Transcription Unit**, **HT Transcription Start Site**, **HT Transcription Termination Site**, **HT Gene Expression**, and **HT NLP Growth Conditions**.

See the documentation page for the arguments and return fields of each query.

## Recommended Workflow

1. Open the documentation page and select the object of interest in the left menu.
2. Review the available queries and their descriptions.
3. Start with a small query (for example, `getAll...` with `limit`) to inspect the structure of the results.
4. Switch to `get...By` queries to retrieve specific records.
5. Use `getDatabaseInfo` to record the RegulonDB release you queried.

## Good Practices

- Request only the fields you need, and use `limit` for large collections.
- Record the query, date, and RegulonDB release for reproducibility.
- Check field names against the documentation after each new release.
- For heavy offline processing, use the downloadable datasets or a local Docker instance instead of many API calls.

## Related Content
- [Dataset Downloads](dataset_downloads.md)
- [Database Dumps](database_dumps.md)
- [Docker Installation Guide](../07_technical_reference/rdb_docker_instance.md)
- [Datamarts (Release Dump)](../07_technical_reference/datamarts/README.md): structure of the collections the API reads from
- [Core Database Collections (Technical Reference)](../07_technical_reference/core_collections/README.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
