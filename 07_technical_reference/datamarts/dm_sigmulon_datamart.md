# Datamart: Sigmulon (`sigmulonDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 7
- **Size of the BSON file:** 9.2 MB

## Purpose

One document per sigma factor with its sigmulon: sigma factor data, transcribed promoters, summary statistics, and citations.

## Used By

GraphQL `getAllSigmulon`, `getSigmulonBy`; sigmulon pages.

## Source (core collections)

Core collections `sigmaFactors`, `promoters`, `transcriptionUnits`, `genes`. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 7 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLISFC00001"` |
| `allCitations` | `array` | 100% | `[{"publication": {"_id": "RDBECOLIPRC14701", "authors": ["Suzuki T"...` |
| `sigmaFactor` | `object` | 100% | `{"_id": "RDBECOLISFC00001", "abbreviatedName": "sigma28", "gene": {...` |
| `statistics` | `object` | 100% | `{"cotranscriptionFactors": 16, "genes": 76, "promoters": 147, "sigm...` |
| `transcribedPromoters` | `array` | 100% | `[{"TSSPosition": 2013205, "_id": "RDBECOLIPMC00020", "boxes": [{"le...` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `allCitations` | `evidence`, `publication` |
| `sigmaFactor` | `_id`, `abbreviatedName`, `gene`, `name`, `sigmulonGenes`, `sigmulonRegulators`, `synonyms` |
| `statistics` | `cotranscriptionFactors`, `genes`, `promoters`, `sigmaFactors`, `transcriptionFactors`, `transcriptionUnits` |
| `transcribedPromoters` | `TSSPosition`, `_id`, `boxes`, `citations`, `name`, `operonId`, `sequence`, `strand`, `transcribedGenes` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLISFC00001",
  "allCitations": [
    {
      "publication": {
        "_id": "RDBECOLIPRC14701",
        "authors": [
          "Suzuki T",
          "Komeda Y"
        ],
        "citation": "Suzuki T, Komeda Y, 1981, Incomplete flagellar structures in Escherichia coli mutants.",
        "pmid": "7007337",
        "title": "Incomplete flagellar structures in Escherichia coli mutants.",
        "url": "https://www.ncbi.nlm.nih.gov/pubmed/7007337",
        "year": 1981
      }
    },
    {
      "publication": {
        "_id": "RDBECOLIPRC14984",
        "authors": [
          "Liu X",
          "Matsumura P"
        ],
        "citation": "Liu X, Matsumura P, 1995, An alternative sigma factor controls transcription of flagellar class-III operons in Escherichia coli: gene sequence, overproduction, ...",
        "pmid": "7590326",
        "title": "An alternative sigma factor controls transcription of flagellar class-III operons in Escherichia coli: gene sequence, overproduction, purification and character...",
        "url": "https://www.ncbi.nlm.nih.gov/pubmed/7590326",
        "year": 1995
      }
    },
    "..."
  ],
  "sigmaFactor": {
    "_id": "RDBECOLISFC00001",
    "abbreviatedName": "sigma28",
    "gene": {
      "_id": "RDBECOLIGNC01323",
      "name": "fliA"
    },
    "name": "RNA polymerase sigma factor FliA",
    "sigmulonGenes": [
      {
        "_id": "RDBECOLIGNC01317",
        "geneOntologyTerms": {
          "biologicalProcess": [
            {
              "_id": "RDBONTOLGON02711",
              "name": "GO:0071973 - bacterial-type flagellum-dependent cell motility"
            }
          ],
          "cellularComponent": [
            {
              "_id": "RDBONTOLGON02489",
              "name": "GO:0005829 - cytosol"
            },
            {
              "_id": "RDBONTOLGON02176",
              "name": "GO:0005886 - plasma membrane"
            },
  ...
```

## Indexes

| Name | Keys |
|---|---|
| `sigmaFactor_name_1` | `{"sigmaFactor.name": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
