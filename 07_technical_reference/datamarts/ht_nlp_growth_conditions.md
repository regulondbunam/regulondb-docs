<img src="../../assets/icons/technical.svg" alt="" width="48">

# Datamart: HT NLP Growth Conditions (`nlpGrowthConditions`)

- **Database:** `regulondbht`
- **Documents (release 14.5.1):** 1,576
- **Size of the BSON file:** 1.7 MB

## Purpose

Growth conditions of HT datasets extracted with natural language processing (NLP).

## Used By

GraphQL **HT NLP Growth Conditions** queries.

## Source (core collections)

NLP extraction (group of Dr. Carlos-Francisco Méndez-Cruz). *(to be validated by the software team)*

## Top-level Fields

Field presence is computed over 1,576 documents (all documents).

| Field | Data type | Present in | Example |
|---|---|---:|---|
| `_id` | `string` | 100% | `"GC_SRR794827"` |
| `aeration` | `array` | 9% | `[{"associated_phrase": "<Air> Aerobic </Air> growth at <Temp> 37 °C...` |
| `datasetIds` | `array` | 100% | `["GENE_EXPRESSION_SRR794827"]` |
| `temperature` | `array` | 45% | `[{"associated_phrase": "<Air> Aerobic </Air> growth at <Temp> 37 °C...` |
| `temporalId` | `string` | 100% | `"GC_GENE_EXPRESSION_SRR794827"` |
| `geneticBackground` | `array` | 67% | |
| `medium` | `array` | 38% | |
| `mediumSupplements` | `array` | 26% | |
| `growthPhase` | `array` | 19% | |
| `opticalDensity` | `array` | 1% | |
| `ph` | `array` | 1% | |

## Nested Structure (second level)

| Field | Subfields |
|---|---|
| `aeration` | `associated_phrase`, `name_field`, `score`, `value` |
| `temperature` | `associated_phrase`, `name_field`, `score`, `value` |
| `geneticBackground` | `associated_phrase`, `name_field`, `score`, `value` |
| `medium` | `associated_phrase`, `name_field`, `score`, `value` |
| `mediumSupplements` | `associated_phrase`, `name_field`, `score`, `value` |
| `growthPhase` | `associated_phrase`, `name_field`, `score`, `value` |
| `opticalDensity` | `associated_phrase`, `name_field`, `score`, `value` |
| `ph` | `associated_phrase`, `name_field`, `score`, `value` |

## Example (first document, simplified)

```json
{
  "_id": "GC_SRR794827",
  "aeration": [
    {
      "associated_phrase": "<Air> Aerobic </Air> growth at <Temp> 37 °C </Temp> in specified media",
      "name_field": "growth_protocol",
      "score": 100,
      "value": "Aerobic"
    }
  ],
  "datasetIds": [
    "GENE_EXPRESSION_SRR794827"
  ],
  "temperature": [
    {
      "associated_phrase": "<Air> Aerobic </Air> growth at <Temp> 37 °C </Temp> in specified media",
      "name_field": "growth_protocol",
      "score": 80,
      "value": "37 °C"
    }
  ],
  "temporalId": "GC_GENE_EXPRESSION_SRR794827"
}
```

## Related Content
- [Datamarts Index](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [API Access (GraphQL)](../../02_data_access/api_access.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
