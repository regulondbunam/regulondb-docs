# Datamart: Regulatory Network (`regulatoryNetworkDatamart`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 5,038
- **Size of the BSON file:** 54.6 MB

## Purpose

Nodes of the regulatory network (genes, transcription factors, and other regulators) with their incoming (`indegree`) and outgoing (`outdegree`) regulatory links.

## Used By

GraphQL **RegulatoryNetwork** queries; network views on regulon pages.

## Source (core collections)

Core collections `regulatoryInteractions`, `regulators`, `genes`. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 5,038).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLITFC00001"` |
| `indegree` | `array` | 66% | `[{"_id": "RDBECOLITFC00104", "citations": [{"evidence": {"_id": "RD...` |
| `name` | `string` | 100% | `"YafC"` |
| `outdegree` | `array` | 12% | `[{"_id": "RDBECOLIGNC00186", "name": "cysJ", "networkType": "TF-Gen...` |
| `type` | `string` | 100% | `"Transcription Factor"` |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `indegree` | `_id`, `citations`, `name`, `networkType`, `regulatoryEffect`, `tooltip`, `type` |
| `outdegree` | `_id`, `citations`, `name`, `networkType`, `regulatoryEffect`, `tooltip`, `type` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLITFC00001",
  "indegree": [
    {
      "_id": "RDBECOLITFC00104",
      "citations": [
        {
          "evidence": {
            "_id": "RDBECOLIEVC00017",
            "code": "EXP-IDA",
            "name": "Inferred from direct assay",
            "type": "W"
          },
          "publication": {
            "_id": "RDBECOLIPRC00970",
            "authors": [
              "Zimmer DP",
              "Soupene E",
              "..."
            ],
            "citation": "Zimmer DP, Soupene E, Lee HL, Wendisch VF, Khodursky AB, Peter BJ, Bender RA, Kustu S, 2000, Nitrogen regulatory protein C-controlled genes of Escherichia coli:...",
            "pmid": "11121068",
            "title": "Nitrogen regulatory protein C-controlled genes of Escherichia coli: scavenging as a defense against nitrogen limitation.",
            "url": "https://www.ncbi.nlm.nih.gov/pubmed/11121068",
            "year": 2000
          }
        },
        {
          "evidence": {
            "_id": "RDBECOLIEVC00056",
            "code": "COMP-HINF-FN-FROM-SEQ",
            "name": "Human inference of function from sequence",
            "type": "W"
          },
          "publication": {
            "_id": "RDBECOLIPRC17111",
            "authors": [
              "Muse WB",
              "Bender RA"
            ],
            "citation": "Muse WB, Bender RA, 1998, The nac (nitrogen assimilation control) gene from Escherichia coli.",
            "pmid": "9495755",
            "title": "The nac (nitrogen assimilation control) gene from Escherichia coli.",
            "url": "https://www.ncbi.nlm.nih.gov/pubmed/9495755",
            "year": 1998
          }
        },
        "..."
      ],
      "name": "Nac",
      "networkType": "TF-TF",
      "regulatoryEffect": "repressor",
      "tooltip": "Transcription Factor Nac represses Transcription Factor YafC",
      "type": "Transcription Factor"
    }
  ],
  "name": "YafC",
  "outdegree": [
    {
      "_id": "RDBECOLIGNC00186",
  ...
```

## Indexes

| Name | Keys |
|---|---|
| `name_1` | `{"name": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
