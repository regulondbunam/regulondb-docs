# Datamart: DNA Features (`dnaFeatures`)

- **Database:** `regulondbdatamarts`
- **Documents (release 14.5.1):** 15,091
- **Size of the BSON file:** 25.5 MB

## Purpose

Genomic features with coordinates and drawing attributes (label, colors, line style, tooltip) used to draw genomic regions. Object types: `tf_binding_site`, `gene`, `promoter`, `terminator`, `srna`, `ppGpp`, `translational_tf_binding_site`.

## Used By

GraphQL **DTT** (Drawing Traces Tool) queries; graphical views of genes, operons, and regulons.

## Source (core collections)

Core collections `genes`, `promoters`, `terminators`, `regulatorySites`, and related objects. *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 3,000 documents (the first 3,000 of 15,091).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"RDBECOLIGNC00001"` |
| `labelFont` | `string` | 100% | `"arial"` |
| `labelName` | `string` | 100% | `"alr"` |
| `labelRGBColor` | `string` | 100% | `"0,0,0"` |
| `labelSize` | `int` | 100% | `12` |
| `leftEndPosition` | `int` | 100% | `4265782` |
| `lineRGBColor` | `string` | 100% | `"0,0,0"` |
| `lineType` | `int` | 100% | `1` |
| `lineWidth` | `int` | 100% | `1` |
| `objectType` | `string` | 100% | `"gene"` |
| `organism` | `object` | 100% | `{"_id": "RDBECOLIORC00001"}` |
| `rightEndPosition` | `int` | 100% | `4266861` |
| `strand` | `string` | 100% | `"forward"` |
| `tooltip` | `string` | 100% | `"Gene: alr;\nSynonyms: ['alr5', 'EG10001']\nLocation: 4265782->4266...` |
| `citations` | `array` | 6% | |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `organism` | `_id` |
| `citations` | `publication` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIGNC00001",
  "labelFont": "arial",
  "labelName": "alr",
  "labelRGBColor": "0,0,0",
  "labelSize": 12,
  "leftEndPosition": 4265782,
  "lineRGBColor": "0,0,0",
  "lineType": 1,
  "lineWidth": 1,
  "objectType": "gene",
  "organism": {
    "_id": "RDBECOLIORC00001"
  },
  "rightEndPosition": 4266861,
  "strand": "forward",
  "tooltip": "Gene: alr;\nSynonyms: ['alr5', 'EG10001']\nLocation: 4265782->4266861;\nProduct: alanine racemase 1"
}
```

## Indexes

| Name | Keys |
|---|---|
| `labelName_1` | `{"labelName": {"$numberInt": "1"}}` |

## Related Pages

- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
