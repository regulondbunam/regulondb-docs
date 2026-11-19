# Datamart: HT Dataset (`dataset`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 2,445
- **Size of the BSON file:** 3.6 MB

## Purpose

Metadata of each high-throughput (HT) dataset: source, publication, sample, experimental conditions, and processing.

## Used By

GraphQL **HT Dataset** queries (`listAllHTSources`, `listAllDatasetTypes`, `listAllDatasetStrategies`, and others); High Throughput collections pages.

## Source (core collections)

HT dataset curation. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 2,445 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"GENE_EXPRESSION_ERR1218301"` |
| `collectionData` | `object` | 100% | `{"source": "REGULONDB", "type": "GENE_EXPRESSION"}` |
| `linkedDataset` | `object` | 100% | `{"datasetType": "GENE_EXPRESSION"}` |
| `releaseDataControl` | `object` | 100% | `{"date": "19/02/2026", "version": "14.1.0"}` |
| `temporalId` | `string` | 100% | `"GENE_EXPRESSION_RNA_SEQ_ERR1218301"` |
| `sample` | `object` | 76% | |
| `sourceSerie` | `object` | 76% | |
| `growthConditions` | `array` | 13% | |
| `referenceGenome` | `string` | 18% | |
| `sourceReferenceGenome` | `string` | 17% | |
| `notes` | `string` | 7% | |
| `objectsTested` | `array` | 19% | |
| `externalReferences` | `array` | 8% | |
| `summary` | `object` | 7% | |
| `cutOff` | `double` | 6% | |
| `assemblyGenomeId` | `string` | 0% | |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `collectionData` | `source`, `type` |
| `linkedDataset` | `controlId`, `datasetType`, `experimentId` |
| `releaseDataControl` | `date`, `version` |
| `sample` | `controlId`, `experimentId`, `title` |
| `sourceSerie` | `method`, `platform`, `series`, `sourceDB`, `strategy`, `title` |
| `growthConditions` | `aeration`, `agitationSpeed`, `experimentId`, `experimentTitle`, `geneticBackground`, `growthPhase`, `medium`, `mediumSupplements`, `opticalDensity`, `organism`, `otherTerms`, `ph`, `temperature`, `vesselType` |
| `objectsTested` | `_id`, `abbreviatedName`, `activeConformations`, `externalCrossReferences`, `genes`, `name`, `note`, `synonyms` |
| `externalReferences` | `description`, `name`, `note`, `url` |
| `summary` | `totalOfPeaks`, `totalOfTFBS` |

## Example (first document, simplified)

```json
{
  "_id": "GENE_EXPRESSION_ERR1218301",
  "collectionData": {
    "source": "REGULONDB",
    "type": "GENE_EXPRESSION"
  },
  "linkedDataset": {
    "datasetType": "GENE_EXPRESSION"
  },
  "releaseDataControl": {
    "date": "19/02/2026",
    "version": "14.1.0"
  },
  "temporalId": "GENE_EXPRESSION_RNA_SEQ_ERR1218301"
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
