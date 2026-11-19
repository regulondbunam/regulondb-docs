# Collection: Segments (`segments`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 18,524

## Purpose

Stores genomic segment objects linked to parent classes (for example terminators or mRNA-related segments).

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 18,524 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% |  | `"\|ACCCT1\|"` |
| `absoluteCenterPosition` | `number` |  | 20% |  | `1825774.5` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `citations` | `array<object>` |  | 68% |  | `[{"publications_id": "RDBECOLIPRC15798"}]` |
| `confidenceLevel` | `string` |  | 0% |  |  |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00018", "objectId": "AC...` |
| `name` | `string` |  | 72% |  | `"Chromosome Region 1, 0->48858"` |
| `leftEndPosition` | `number` |  | 34% |  | `3407286` |
| `rightEndPosition` | `number` |  | 34% |  | `3407302` |
| `parentClass` | `string` |  | 100% |  | `"\|Terminators\|"` |
| `strand` | `string` |  | 100% | values: `forward`, `reverse` | `"forward"` |
| `type` | `string` | yes | 100% |  | `"\|mRNA-Segments\|"` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |

## Example (first document, simplified)

```json
{
  "_id": "|ACCCT1|",
  "citations": [
    {
      "publications_id": "RDBECOLIPRC15798"
    }
  ],
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00018",
      "objectId": "ACCCT1"
    }
  ],
  "leftEndPosition": 3407286,
  "parentClass": "|Terminators|",
  "rightEndPosition": 3407302,
  "strand": "forward",
  "type": "|mRNA-Segments|"
}
```

## Main Relationships

- Supports structural mapping around transcriptional objects.

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
