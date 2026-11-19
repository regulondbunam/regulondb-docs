# Datamart: Database Info (`databaseInfo`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 59
- **Size of the BSON file:** 222.3 KB

## Purpose

Metadata of each RegulonDB release: version, release date, EcoCyc and genome versions, release note, content statistics, and the route of the release download.

## Used By

GraphQL `getDatabaseInfo`; **Releases & Downloads** pages (release history and release notes).

## Source (core collections)

Release process metadata. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 59 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `ObjectId` | 100% | `"697a69139d37a20f3a61ac03"` |
| `releaseDate` | `string` | 100% | `"2026-11-11"` |
| `localData` | `array` | 100% | `[{"type": "XLSX", "sourceName": "RegulonDB_Evidence_Catalog_v3.2", ...` |
| `ecocycVersion` | `string` | 100% | `"29.5"` |
| `regulonDBVersion` | `string` | 100% | `"14.5.1"` |
| `lcVersion` | `string` | 14% | `"1.0.0"` |
| `note` | `string` | 100% | `"# RegulonDB release note\n\n### General Information\n\nRegulonDB v...` |
| `genomeVersion` | `string` | 100% | `"NC_000913.3"` |
| `genomeId` | `string` | 15% | `"556503834"` |
| `statistics` | `object` | 88% | `{"evidences": {"total": 115, "weak": 0, "strong": 0, "confirmed": 0...` |
| `route` | `string` | 100% | `"/dump/rdb-mongo/regulondb_14.5.zip"` |
| `regulondbPMID` | `string` | 86% | |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `localData` | `note`, `responsible`, `sourceName`, `type`, `version` |
| `statistics` | `attenuators`, `effectors`, `evidences`, `externalDBSources`, `externalDataSources`, `externalReferences`, `functConfTF`, `functionalClasses`, `genes`, `gensorUnits`, `motifs`, `ontologies`, `operon`, `organisms`, `product`, `products`, `promoters`, `publications`, `regulatorBindingSites`, `regulatoryComplexes`, `regulatoryContinuants`, `regulatoryInteractions`, `regulons`, `riboswitches`, `segments`, `shineDalgarnos`, `sigmaFactors`, `srnaInteractions`, `synonyms`, `terminators` … |

## Example (first document, simplified)

```json
{
  "_id": "697a69139d37a20f3a61ac03",
  "releaseDate": "2026-11-11",
  "localData": [
    {
      "type": "XLSX",
      "sourceName": "RegulonDB_Evidence_Catalog_v3.2",
      "version": "3.2.0",
      "note": "Local Evidences",
      "responsible": "Felipe Betancourt Figueroa"
    }
  ],
  "ecocycVersion": "29.5",
  "regulonDBVersion": "14.5.1",
  "lcVersion": "1.0.0",
  "note": "# RegulonDB release note\n\n### General Information\n\nRegulonDB version 14.5\n\nEcocyc version 29.5\n\n### **Summary of New Content and Updates**\n\nRegulonDB 14.5 is do...",
  "genomeVersion": "NC_000913.3",
  "genomeId": "556503834",
  "statistics": {
    "evidences": {
      "total": 115,
      "weak": 0,
      "strong": 0,
      "confirmed": 0,
      "withoutEvidence": 115,
      "withEvidence": 0
    },
    "externalReferences": {
      "total": 32475,
      "origin": {
        "promoter": 1363,
        "gene": 313,
        "product": 27785,
        "regulator": 2904,
        "regulatoryComplex": 2017,
        "regulatoryContinuant": 70,
        "sigmaFactor": 364,
        "terminator": 266,
        "transcriptionUnit": 1946,
        "regulatoryInteraction": 1920
      }
    },
    "externalDBSources": {
      "total": 132921,
      "origin": {
        "ecocyc": 59395,
        "refseq": 8943,
        "asap": 4458,
        "ecoliwiki": 4433,
        "uniprot": 4407,
        "others": 51285
      }
    },
    "genes": {
      "total": 4748,
      "weak": 0,
      "strong": 0,
      "confirmed": 0,
      "withoutEvidence": 4748,
      "withEvidence": 0
  ...
```

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
