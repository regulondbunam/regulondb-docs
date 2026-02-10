# Collection: Segments

## Purpose

Stores genomic segment objects linked to parent classes (for example terminators or mRNA-related segments).

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Segment identifier | `string` | `|ACCCT1|` |
| `type` | Segment type/class | `string` | `|mRNA-Segments|` |
| `parentClass` | Parent class grouping | `string` | `|Terminators|` |
| `leftEndPosition` | Segment start coordinate | `integer` | `3407286` |
| `rightEndPosition` | Segment end coordinate | `integer` | `3407302` |
| `strand` | Segment strand orientation | `string` | `forward` |
| `citations` | Supporting publications | `array<object>` | `[{"publications_id":"RDBECOLIPRC26301"}]` |
| `externalCrossReferences` | External mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00013","objectId":"ACCCT1"}]` |

## Example (simplified)

```json
{
  "_id": "|ACCCT1|",
  "parentClass": "|Terminators|",
  "leftEndPosition": 3407286,
  "rightEndPosition": 3407302
}
```

## Main Relationships

- Supports structural mapping around transcriptional objects.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
