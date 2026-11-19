# Collection: Transcription Factors (`transcriptionFactors`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 243

## Purpose

Stores transcription-factor specific objects, including active/inactive conformations and functional properties.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 243 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% |  | `"RDBECOLITFC00214"` |
| `abbreviatedName` | `string` |  | 100% |  | `"PunR"` |
| `activeConformations` | `array<object>` |  | 94% |  | `[{"_id": "RDBECOLIPDC01427", "type": "product"}]` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `citations` | `array<object>` |  | 100% |  | `[{"publications_id": "RDBECOLIPRC01314"}, {"evidences_id": "RDBECOL...` |
| `confidenceLevel` | `string` |  | 97% |  | `"W"` |
| `connectivityClass` | `string` |  | 0% |  |  |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00004", "objectId": "P0...` |
| `globalFunction` | `string` |  | 100% | values: `activator`, `repressor`, `dual` | `"activator"` |
| `inactiveConformations` | `array<object>` |  | 21% |  | `[{"_id": "RDBECOLIRCC00127", "type": "regulatoryComplex"}]` |
| `name` | `string` |  | 100% |  | `"DNA-binding transcriptional activator PunR"` |
| `note` | `string` |  | 64% |  | `"PunR, formerly named YdhB, regulates a gene involved in the purine...` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `products_ids` | `array<string>` |  | 100% |  | `["RDBECOLIPDC01427"]` |
| `sensingClass` | `string` |  | 0% |  |  |
| `siteLength` | `array<number>` |  | 49% |  | `[18]` |
| `synonyms` | `array<string>` |  | 100% |  | `["PunR", "putative LysR family DNA-binding transcriptional regulato...` |
| `schemaVersion` | `number` |  | 0% |  |  |
| `symmetry` | `array<string>` |  | 75% |  | `["\|INVERTED-REPEAT\|"]` |
| `family` | `string` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `activeConformations` | `_id`, `type` |
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `inactiveConformations` | `_id`, `type` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLITFC00214",
  "abbreviatedName": "PunR",
  "activeConformations": [
    {
      "_id": "RDBECOLIPDC01427",
      "type": "product"
    }
  ],
  "citations": [
    {
      "publications_id": "RDBECOLIPRC01314"
    },
    {
      "evidences_id": "RDBECOLIEVC00072",
      "publications_id": "RDBECOLIPRC03267"
    },
    "..."
  ],
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00004",
      "objectId": "P0ACR2"
    },
    {
      "externalCrossReferences_id": "RDBECOLIERC00025",
      "objectId": "IPR005119"
    },
    "..."
  ],
  "globalFunction": "activator",
  "name": "DNA-binding transcriptional activator PunR",
  "note": "PunR, formerly named YdhB, regulates a gene involved in the purine transport process in the presence of adenosine |CITS:...",
  "organisms_id": "RDBECOLIORC00001",
  "products_ids": [
    "RDBECOLIPDC01427"
  ],
  "symmetry": [
    "|INVERTED-REPEAT|"
  ],
  "synonyms": [
    "PunR",
    "putative LysR family DNA-binding transcriptional regulator YdhB",
    "..."
  ]
}
```

## Main Relationships

- `products_ids[]` -> products collection
- `activeConformations[]` / `inactiveConformations[]` -> product or complex objects
- `citations[]` -> evidences/publications

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
