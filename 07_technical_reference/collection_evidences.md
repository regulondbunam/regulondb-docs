# Collection: Evidences

## Purpose

Defines evidence vocabulary used to support curation confidence and provenance across RegulonDB objects.

## Key Fields

| Field | Description | Data type | Example |
|---|---|---|---|
| `_id` | Stable evidence identifier | `string` | `RDBECOLIEVC00003` |
| `code` | Evidence code | `string` | `EXP-IDA-UNPURIFIED-PROTEIN-NH` |
| `name` | Human-readable evidence name | `string` | `Assay of unpurified protein expressed in its native host` |
| `type` | Evidence confidence/type code | `string` | `W` |
| `evidenceCategory` | Category label | `string` | `Classical experiment` |
| `pertainsTo` | Biological object domains | `array<string>` | `["Enzymatic-Reactions", "Proteins"]` |
| `note` | Full technical evidence description | `string` | `Direct assay of unpurified protein...` |
| `noteWeb` | Web-formatted note | `string` | `Direct assay of unpurified protein...<br>` |
| `head` | Linked parent evidence term | `string` | `RDBECOLIEVC00055` |
| `externalCrossReferences` | External mappings | `array<object>` | `[{"externalCrossReferences_id":"RDBECOLIERC00013","objectId":"EV-EXP-IDA-UNPURIFIED-PROTEIN-NH"}]` |

## Example (simplified)

```json
{
  "_id": "RDBECOLIEVC00003",
  "code": "EXP-IDA-UNPURIFIED-PROTEIN-NH",
  "name": "Assay of unpurified protein expressed in its native host",
  "evidenceCategory": "Classical experiment",
  "type": "W"
}
```

## Main Relationships

- Referenced from `citations[].evidences_id` in multiple collections.
- `externalCrossReferences[].externalCrossReferences_id` -> external cross-reference catalog.

## Notes

- `type` is used in confidence workflows (for example weak/strong categories).
- Evidence records are reused across genes, promoters, TUs, and regulatory interactions.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
