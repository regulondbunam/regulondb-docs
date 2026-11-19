# Datamart: Operon (`operonDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 2,605
- **Size of the BSON file:** 66.8 MB

## Purpose

One document per operon with everything shown on the operon page: operon data, transcription units, promoters, terminators, regulatory interactions, and citations.

## Used By

GraphQL `getAllOperon`, `getOperonBy`; operon pages.

## Source (core collections)

Core collections `operons`, `transcriptionUnits`, `promoters`, `terminators`, `regulatoryInteractions`, `regulatorySites`, `publications`. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 2,605 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLIOPC00001"` |
| `allCitations` | `array` | 100% | `[{"publication": {"_id": "RDBECOLIPRC14473", "authors": ["Hudson GS...` |
| `operon` | `object` | 100% | `{"_id": "RDBECOLIOPC00001", "name": "pheLA", "regulationPositions":...` |
| `organism` | `object` | 100% | `{"_id": "RDBECOLIORC00001"}` |
| `transcriptionUnits` | `array` | 100% | `[{"_id": "RDBECOLITUC02550", "citations": [{"publication": {"_id": ...` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `allCitations` | `evidence`, `publication` |
| `operon` | `_id`, `name`, `regulationPositions`, `statistics`, `strand` |
| `organism` | `_id` |
| `transcriptionUnits` | `_id`, `additiveEvidences`, `citations`, `confidenceLevel`, `firstGene`, `genes`, `name`, `note`, `promoter`, `regulatorBindingSites`, `statistics`, `synonyms`, `terminators` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIOPC00001",
  "allCitations": [
    {
      "publication": {
        "_id": "RDBECOLIPRC14473",
        "authors": [
          "Hudson GS",
          "Davidson BE"
        ],
        "citation": "Hudson GS, Davidson BE, 1984, Nucleotide sequence and transcription of the phenylalanine and tyrosine operons of Escherichia coli K12.",
        "pmid": "6396419",
        "title": "Nucleotide sequence and transcription of the phenylalanine and tyrosine operons of Escherichia coli K12.",
        "url": "https://www.ncbi.nlm.nih.gov/pubmed/6396419",
        "year": 1984
      }
    },
    {
      "evidence": {
        "_id": "RDBECOLIEVC00083",
        "additiveEvidenceCodeRule": 11,
        "code": "EXP-IDA-TRANSCRIPT-LEN-DETERMINATION",
        "name": "Length of transcript experimentally determined",
        "type": "S"
      }
    },
    "..."
  ],
  "operon": {
    "_id": "RDBECOLIOPC00001",
    "name": "pheLA",
    "regulationPositions": {
      "leftEndPosition": 2737579,
      "rightEndPosition": 2738940
    },
    "statistics": {
      "genes": 2,
      "promoters": 1,
      "transcriptionUnits": 1
    },
    "strand": "forward"
  },
  "organism": {
    "_id": "RDBECOLIORC00001"
  },
  "transcriptionUnits": [
    {
      "_id": "RDBECOLITUC02550",
      "citations": [
        {
          "publication": {
            "_id": "RDBECOLIPRC14473",
            "authors": [
              "Hudson GS",
              "Davidson BE"
            ],
            "citation": "Hudson GS, Davidson BE, 1984, Nucleotide sequence and transcription of the phenylalanine and tyrosine operons of Escherichia coli K12.",
            "pmid": "6396419",
            "title": "Nucleotide sequence and transcription of the phenylalanine and tyrosine operons of Escherichia coli K12.",
            "url": "https://www.ncbi.nlm.nih.gov/pubmed/6396419",
  ...
```

## Indexes

| Name | Keys |
|---|---|
| `operon_name_1` | `{"operon.name": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
