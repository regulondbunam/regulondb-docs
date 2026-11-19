# Datamart: Downloadable Files (`downloadableFilesDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 24
- **Size of the BSON file:** 28.5 MB

## Purpose

The downloadable datasets of the **Downloadable Experimental Datasets** page (for example, `RISet`, `TF-RISet`, `GeneProductSet`): file name, title, description, column details, license header, RegulonDB version, and the file content.

## Used By

GraphQL `getDataOfFile`, `listAllFileNames`, `listAllDownloadableFiles`; datasets page and Browse & Filter tool.

## Source (core collections)

Generated from the core collections at each release. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 24 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLIDLF00001"` |
| `citation` | `string` | 100% | `"# Heladia Salgado, Socorro Gama-Castro, et al., RegulonDB v12.0: a...` |
| `columnsDetails` | `string` | 96% | `"# Columns:\n# (1) id. Regulatory interaction (RI) identifier assig...` |
| `contact` | `object` | 100% | `{"email": "regulondb@ccg.unam.mx", "person": "RegulonDB Team", "web...` |
| `content` | `string` | 100% | `"1)id\t2)type\t3)regulatorId\t4)regulatorName\t5)cnfName\t6)tfrsID\...` |
| `creationDate` | `string` | 100% | `"11-11-2026"` |
| `description` | `string` | 100% | `"Regulatory interactions between a Regulator and its regulated enti...` |
| `fileFormat` | `string` | 100% | `"rif-version 1"` |
| `fileName` | `string` | 100% | `"RISet"` |
| `group` | `string` | 100% | `"REGULATORY INTERACTION"` |
| `license` | `string` | 100% | `"# RegulonDB is free for academic/noncommercial use\n# User is not ...` |
| `rdbVersion` | `string` | 100% | `"14.5.1"` |
| `title` | `string` | 100% | `"Complete RIs Set"` |
| `version` | `string` | 100% | `"1.0"` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `contact` | `email`, `person`, `webPage` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIDLF00001",
  "citation": "# Heladia Salgado, Socorro Gama-Castro, et al., RegulonDB v12.0: a comprehensive resource of transcriptional regulation in E. coli K-12,\n# Nucleic Acids Researc...",
  "columnsDetails": "# Columns:\n# (1) id. Regulatory interaction (RI) identifier assigned by RegulonDB\n# (2) type. Regulatory interaction type [TF-promoter, TF-TU, tf-gene,sRNA-prom...",
  "contact": {
    "email": "regulondb@ccg.unam.mx",
    "person": "RegulonDB Team",
    "webPage": null
  },
  "content": "1)id\t2)type\t3)regulatorId\t4)regulatorName\t5)cnfName\t6)tfrsID\t7)tfrsLeft\t8)tfrsRight\t9)strand\t10)tfrsSeq\t11)riFunction\t12)promoterID\t13)promoterName\t14)tss\t15)si...",
  "creationDate": "11-11-2026",
  "description": "Regulatory interactions between a Regulator and its regulated entity -promoter, gene, or transcriptional units.",
  "fileFormat": "rif-version 1",
  "fileName": "RISet",
  "group": "REGULATORY INTERACTION",
  "license": "# RegulonDB is free for academic/noncommercial use\n# User is not entitled to change or erase data sets of the RegulonDB\n# database or to eliminate copyright not...",
  "rdbVersion": "14.5.1",
  "title": "Complete RIs Set",
  "version": "1.0"
}
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
