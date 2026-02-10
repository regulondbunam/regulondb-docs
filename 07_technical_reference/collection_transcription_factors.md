# Collection: Transcription Factors

## Purpose

Stores transcription-factor specific objects, including active/inactive conformations and functional properties.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable TF identifier | `string` | `RDBECOLITFC00020` |
| `name` | Full TF name | `string` | `DNA-binding transcriptional dual regulator H-NS` |
| `abbreviatedName` | Short TF symbol | `string` | `H-NS` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |
| `products_ids` | Linked product IDs | `array<string>` | `["RDBECOLIPDC03940"]` |
| `activeConformations` | Active conformation references | `array<object>` | `[{"_id":"RDBECOLIPDC03940","type":"product"}]` |
| `inactiveConformations` | Inactive conformation references | `array<object>` | `[{"_id":"RDBECOLIRCC01000","type":"regulatoryComplex"}]` |
| `globalFunction` | Global regulatory function label | `string` | `dual` |
| `siteLength` | Binding-site length metadata | `number` | `14` |
| `symmetry` | Symmetry descriptor | `string` | `palindrome` |
| `confidenceLevel` | Confidence label | `string` | `W` |
| `citations` | Supporting evidence/publication links | `array<object>` | `[{"evidences_id":"RDBECOLIEVC00036","publications_id":"RDBECOLIPRC02078"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLITFC00020",
  "abbreviatedName": "H-NS",
  "organisms_id": "RDBECOLIORC00001"
}
```

## Main Relationships

- `products_ids[]` -> products collection
- `activeConformations[]` / `inactiveConformations[]` -> product or complex objects
- `citations[]` -> evidences/publications

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
