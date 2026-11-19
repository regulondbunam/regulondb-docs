<img src="../../assets/icons/technical.svg" alt="" width="48">

# Datamart: Gene (`geneDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 4,748
- **Size of the BSON file:** 132.7 MB

## Purpose

One document per gene with everything shown on the gene page: gene data, products, regulation (operons, promoters, regulators), organism, and citations.

## Used By

GraphQL `getAllGenes`, `getGenesBy`; gene pages.

## Source (core collections)

Core collections `genes`, `products`, `operons`, `transcriptionUnits`, `promoters`, `regulatoryInteractions`, `publications`, `evidences`. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 4,748).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLIGNC00001"` |
| `allCitations` | `array` | 97% | `[{"evidence": {"_id": "RDBECOLIEVC00036", "additiveEvidenceCodeRule...` |
| `gene` | `object` | 100% | `{"_id": "RDBECOLIGNC00001", "bnumber": "b4053", "centisomePosition"...` |
| `organism` | `object` | 100% | `{"_id": "RDBECOLIORC00001"}` |
| `products` | `array` | 98% | `[{"_id": "RDBECOLIPDC00061", "abbreviatedName": "Alr", "cellularLoc...` |
| `regulation` | `object` | 94% | `{"operon": {"_id": "RDBECOLIOPC02693", "arrangement": [{"promoters"...` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `allCitations` | `evidence`, `publication` |
| `gene` | `_id`, `bnumber`, `centisomePosition`, `citations`, `externalCrossReferences`, `fragments`, `gcContent`, `leftEndPosition`, `name`, `note`, `rightEndPosition`, `sequence`, `strand`, `synonyms`, `type` |
| `organism` | `_id` |
| `products` | `_id`, `abbreviatedName`, `anticodon`, `cellularLocations`, `citations`, `externalCrossReferences`, `geneOntologyTerms`, `molecularWeight`, `motifs`, `name`, `note`, `regulonId`, `sequence`, `synonyms`, `type` |
| `regulation` | `operon`, `regulators`, `statistics` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIGNC00001",
  "allCitations": [
    {
      "evidence": {
        "_id": "RDBECOLIEVC00036",
        "additiveEvidenceCodeRule": 7,
        "code": "COMP-AINF",
        "name": "Inferred computationally without human oversight",
        "type": "W"
      },
      "publication": {
        "_id": "RDBECOLIPRC17544",
        "authors": [
          "GOA",
          "DDB",
          "..."
        ],
        "citation": "GOA, DDB, FB, MGI, ZFIN, 2001, Gene Ontology annotation through association of InterPro records with GO terms.",
        "title": "Gene Ontology annotation through association of InterPro records with GO terms.",
        "url": "https://github.com/geneontology/go-site/blob/master/metadata/gorefs/goref-0000002.md",
        "year": 2001
      }
    },
    {
      "evidence": {
        "_id": "RDBECOLIEVC00036",
        "additiveEvidenceCodeRule": 7,
        "code": "COMP-AINF",
        "name": "Inferred computationally without human oversight",
        "type": "W"
      },
      "publication": {
        "_id": "RDBECOLIPRC17556",
        "authors": [
          "UniProt"
        ],
        "citation": "UniProt, 2021, Electronic Gene Ontology annotations created by ARBA machine learning models",
        "title": "Electronic Gene Ontology annotations created by ARBA machine learning models",
        "url": "https://github.com/geneontology/go-site/blob/master/metadata/gorefs/goref-0000117.md",
        "year": 2021
      }
    },
    "..."
  ],
  "gene": {
    "_id": "RDBECOLIGNC00001",
    "bnumber": "b4053",
    "centisomePosition": 91.90224,
    "externalCrossReferences": [
      {
        "externalCrossReferenceId": "RDBECOLIERC00006",
        "externalCrossReferenceName": "ASKA",
        "objectId": "ECK4045+b4053+JW4013+alr",
        "url": "https://shigen.nig.ac.jp/ecoli/strain/quicksearch/list?keyword=ECK4045+b4053+JW4013+alr#quicksearchListAskaCloneMinus"
      },
      {
        "externalCrossReferenceId": "RDBECOLIERC00026",
        "externalCrossReferenceName": "KEIO",
        "objectId": "ECK4045+b4053+JW4013+alr",
  ...
```

## Indexes

| Name | Keys |
|---|---|
| `gene_name_1` | `{"gene.name": {"$numberInt": "1"}}` |

## Related Content
- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
