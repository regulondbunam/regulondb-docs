# Datamart: Regulon (`regulonDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 290
- **Size of the BSON file:** 150.2 MB

## Purpose

One document per regulon with everything shown on the regulon page: regulator, regulated objects (genes, operons, transcription units), regulatory interactions, summary counts, GO terms, and citations.

## Used By

GraphQL `getAllRegulon`, `getRegulonBy`; regulon pages and catalog.

## Source (core collections)

Core collections `regulators`, `transcriptionFactors`, `regulatoryInteractions`, `regulatorySites`, `genes`, `operons`, `transcriptionUnits`, `publications`. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 290 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLICNC00080"` |
| `allCitations` | `array` | 100% | `[{"publication": {"_id": "RDBECOLIPRC13193", "authors": ["Singh V",...` |
| `regulates` | `object` | 100% | `{"genes": [{"_id": "RDBECOLIGNC02514", "function": "repressor", "na...` |
| `regulator` | `object` | 100% | `{"_id": "RDBECOLICNC00080", "abbreviatedName": "ppGpp", "name": "pp...` |
| `regulatoryInteractions` | `array` | 100% | `[{"_id": "RDBECOLIRIC00552", "activeConformation": {"_id": "RDBECOL...` |
| `summary` | `object` | 100% | `{"bindingSites": {"activated": 0, "dual": 0, "repressed": 0, "total...` |
| `terms` | `object` | 99% | |
| `organism` | `object` | 83% | |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `allCitations` | `evidence`, `publication` |
| `regulates` | `genes`, `operons`, `sigmaFactors`, `transcriptionFactors`, `transcriptionUnits` |
| `regulator` | `_id`, `abbreviatedName`, `citations`, `confidenceLevel`, `conformations`, `encodedBy`, `name`, `note`, `products`, `siteLength`, `symmetry`, `synonyms`, `type` |
| `regulatoryInteractions` | `_id`, `activeConformation`, `additiveEvidences`, `citations`, `confidenceLevel`, `distanceToFirstGene`, `distanceToPromoter`, `function`, `mechanism`, `regulatedEntity`, `regulatedGenes`, `regulatoryBindingSites` |
| `summary` | `bindingSites`, `genes`, `operons`, `regulatoryInteractions`, `sigmaFactors`, `transcriptionFactors`, `transcriptionUnits` |
| `terms` | `geneOntology` |
| `organism` | `_id` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLICNC00080",
  "allCitations": [
    {
      "publication": {
        "_id": "RDBECOLIPRC13193",
        "authors": [
          "Singh V",
          "Harinarayanan R"
        ],
        "citation": "Singh V, Harinarayanan R, 2024, (p)ppGpp Buffers Cell Division When Membrane Fluidity Decreases in Escherichia coli.",
        "pmid": "39461000",
        "title": "(p)ppGpp Buffers Cell Division When Membrane Fluidity Decreases in Escherichia coli.",
        "url": "https://www.ncbi.nlm.nih.gov/pubmed/39461000",
        "year": 2024
      }
    },
    {
      "evidence": {
        "_id": "RDBECOLIEVC00081",
        "code": "EXP-IMP",
        "name": "Inferred from mutant phenotype",
        "type": "W"
      },
      "publication": {
        "_id": "RDBECOLIPRC16983",
        "authors": [
          "Safo MK",
          "Yang WZ",
          "..."
        ],
        "citation": "Safo MK, Yang WZ, Corselli L, Cramton SE, Yuan HS, Johnson RC, 1997, The transactivation region of the fis protein that controls site-specific DNA inversion con...",
        "pmid": "9362499",
        "title": "The transactivation region of the fis protein that controls site-specific DNA inversion contains extended mobile beta-hairpin arms.",
        "url": "https://www.ncbi.nlm.nih.gov/pubmed/9362499",
        "year": 1997
      }
    },
    "..."
  ],
  "regulates": {
    "genes": [
      {
        "_id": "RDBECOLIGNC02514",
        "function": "repressor",
        "name": "rrlA",
        "terms": {}
      },
      {
        "_id": "RDBECOLIGNC02446",
        "function": "repressor",
        "name": "alaT",
        "terms": {
          "geneOntology": {
            "cellularComponent": [
              {
                "_id": "RDBONTOLGON05398",
                "name": "GO:0005737 - cytoplasm"
              },
              {
  ...
```

## Indexes

| Name | Keys |
|---|---|
| `regulator_name_1` | `{"regulator.name": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
