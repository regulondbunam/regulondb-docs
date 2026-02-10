# Collection: Regulatory Interactions

## Purpose

Represents regulatory links between a regulator and a regulated entity (for example promoter or transcription unit), including function and supporting citations.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable interaction identifier | `string` | `RDBECOLIRIC00001` |
| `regulator` | Regulator object reference | `object` | `{"_id":"RDBECOLIPDC01486","type":"product"}` |
| `regulatedEntity` | Regulated target reference | `object` | `{"_id":"RDBECOLIPMC03419","type":"promoter"}` |
| `function` | Regulatory effect | `string` | `repressor` |
| `regulationType` | Regulation level/type | `string` | `Transcription` |
| `regulationClass` | Regulatory class tag(s) | `array<string>` | `["|Transcription-Factor-Binding|"]` |
| `relativeDistSitePromoter` | Distance from site to promoter | `number` | `-60.5` |
| `regulatorySites_id` | Linked regulatory site identifier | `string` | `RDBECOLIBSC01689` |
| `confidenceLevel` | Confidence label | `string` | `W` |
| `citations` | Supporting evidence/publication links | `array<object>` | `[{"evidences_id":"RDBECOLIEVC00005","publications_id":"RDBECOLIPRC04176"}]` |
| `organisms_id` | Linked organism identifier | `string` | `RDBECOLIORC00001` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIRIC00001",
  "function": "repressor",
  "regulationType": "Transcription",
  "regulator": { "_id": "RDBECOLIPDC01486", "type": "product" },
  "regulatedEntity": { "_id": "RDBECOLIPMC03419", "type": "promoter" },
  "confidenceLevel": "W"
}
```

## Main Relationships

- `regulator._id` -> regulator/product object
- `regulatedEntity._id` -> promoter/TU/other regulated objects
- `regulatorySites_id` -> regulatory sites collection
- `citations[].evidences_id` -> evidences collection

## Notes

- This collection is central for reconstructing regulatory networks.
- Distances can be used for promoter-proximal analysis.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
