<img src="../../assets/icons/technical.svg" alt="" width="48">

# Collection: Organisms (`organisms`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 1

## Purpose

Intended to store organism-level metadata referenced by `organisms_id` fields.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 1 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORG00001"` |
| `description` | `string` |  | 100% |  | `"EcoCyc is a model-organism database for <i>Escherichia coli</i> K-...` |
| `internalComment` | `string` |  | 0% |  |  |
| `genome` | `string` |  | 100% |  | `"\|COLI-K12\|"` |
| `name` | `string` | yes | 100% |  | `"Escherichia coli"` |
| `pgdbAuthors` | `array<string>` |  | 100% |  | `["\|pkarp\|", "\|paley\|", "\|kr\|", "\|kothari\|", "\|keseler\|", ...` |
| `pgdbCopyright` | `string` |  | 100% |  | `"Copyright SRI International 1999-2023, Marine Biological Laborator...` |
| `pgdbName` | `string` |  | 100% |  | `"EcoCyc"` |
| `strainName` | `string` |  | 100% |  | `"K-12 substr. MG1655"` |
| `synonyms` | `array<string>` |  | 100% |  | `["Escherichia coli K-12 substr. MG1655", "ECOLI"]` |
| `url` | `string` |  | 100% |  | `"<a href=\"https://www.frontiersin.org/articles/10.3389/fmicb.2021....` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIORG00001",
  "description": "EcoCyc is a model-organism database for <i>Escherichia coli</i> K-12 MG1655, the strain from which the first complete ge...",
  "genome": "|COLI-K12|",
  "name": "Escherichia coli",
  "pgdbAuthors": [
    "|pkarp|",
    "|paley|",
    "..."
  ],
  "pgdbCopyright": "Copyright SRI International 1999-2023, Marine Biological Laboratory 1998-2001, DoubleTwist Inc 1998-1999.  All Rights Re...",
  "pgdbName": "EcoCyc",
  "strainName": "K-12 substr. MG1655",
  "synonyms": [
    "Escherichia coli K-12 substr. MG1655",
    "ECOLI"
  ],
  "url": "<a href=\"https://www.frontiersin.org/articles/10.3389/fmicb.2021.711077/full\">Frontiers in Microbiology 2021</a>"
}
```

## Related Content
- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
