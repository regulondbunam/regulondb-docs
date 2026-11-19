# Collection: Products (`products`)

- **Database:** `regulondbmultigenomic` (core collections)
- **Documents (release 14.5.1):** 4,664

## Purpose

Stores gene products (proteins and other functional products), including biochemical attributes and cross-references.

## Fields

Data types, required fields, and identifier patterns come from the JSON Schema used to validate the collection; presence is computed over the 4,664 documents of release 14.5.1.

| Field | Data type | Required | Present in | Constraints | Example |
|---|---|:---:|---:|---|---|
| `_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIPDC00001"` |
| `abbreviatedName` | `string` |  | 100% |  | `"PlsC"` |
| `additiveEvidences` | `array<string>` |  | 0% |  |  |
| `anticodon` | `string` |  | 2% |  | `"UAC"` |
| `catalyzes` | `array<string>` |  | 19% |  | `["acyl-[acp]:1-acyl-sn-glycerol-3-phosphate 2-<i>O</i>-acyltransfer...` |
| `codingSegments` | `array<array>` |  | 1% |  | `[[292, 1965]]` |
| `componentOf` | `array<string>` |  | 35% |  | `["1-phosphofructokinase"]` |
| `consensusSequences` | `array<string>` |  | 2% |  | `["[AT]TGTTA[AT][TA][AT]A[AT][AT]TGTT[AG][AC]\|CITS: [34824476]\|"]` |
| `citations` | `array<object>` |  | 57% |  | `[{"publications_id": "RDBECOLIPRC03152"}, {"publications_id": "RDBE...` |
| `confidenceLevel` | `string` |  | 23% |  | `"W"` |
| `externalCrossReferences` | `array<object>` |  | 100% |  | `[{"externalCrossReferences_id": "RDBECOLIERC00004", "objectId": "P2...` |
| `genes_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIGNC01344"` |
| `internalComment` | `string` |  | 100% |  | `"; Source: EcoCyc"` |
| `isoelectricPoints` | `array<number>` |  | 12% |  | `[9.76]` |
| `isTranscriptionFactor` | `boolean` |  | 0% |  |  |
| `locations` | `array<string>` |  | 88% |  | `["inner membrane"]` |
| `modifiedForms` | `array<string>` |  | 4% |  | `["DNA-binding transcriptional dual regulator ArcA-phosphorylated"]` |
| `molecularWeight` | `number` |  | 93% |  | `27.453001` |
| `molecularWeightsKd` | `array<number>` |  | 93% |  | `[27.453001, 25.0]` |
| `name` | `string` |  | 100% |  | `"1-acylglycerol-3-phosphate <i>O</i>-acyltransferase PlsC"` |
| `note` | `string` |  | 86% |  | `"Membrane-bound 1-acylglycerol-3-phosphate <i>O</i>-acyltransferase...` |
| `organisms_id` | `string` | yes | 100% | pattern `^RDB[A-Z]{8}[0-9]{5}$` | `"RDBECOLIORC00001"` |
| `sequence` | `string` |  | 100% |  | `"MLYIFRLIITVIYSILVCVFGSIYCLFSPRNPKHVATFGHMFGRLAPLFGLKVECRKPTDAESYGN...` |
| `siteLength` | `array<number>` |  | 2% |  | `[7]` |
| `spliceFormIntrons` | `array<array>` |  | 0% |  |  |
| `symmetries` | `array<string>` |  | 4% |  | `["inverted-repeat"]` |
| `synonyms` | `array<string>` |  | 98% |  | `["ParF", "PlsC"]` |
| `terms` | `object` |  | 95% |  | `{"biologicalProcess": [{"citations": [{"evidences_id": "RDBECOLIEVC...` |
| `type` | `string` |  | 5% |  | `"small RNA"` |
| `schemaVersion` | `number` |  | 0% |  |  |

## Nested Structure

| Field | Subfields |
|---|---|
| `citations` | `publications_id`, `evidences_id` |
| `externalCrossReferences` | `externalCrossReferences_id`, `objectId` |
| `terms` | `biologicalProcess`, `cellularComponent`, `molecularFunction` |

## Example (first document, simplified)

```json
{
  "_id": "RDBECOLIPDC00001",
  "abbreviatedName": "PlsC",
  "catalyzes": [
    "acyl-[acp]:1-acyl-sn-glycerol-3-phosphate 2-<i>O</i>-acyltransferase",
    "acyl-CoA:1-acyl-sn-glycerol-3-phosphate 2-<i>O</i>-acyltransferase"
  ],
  "citations": [
    {
      "publications_id": "RDBECOLIPRC03152"
    },
    {
      "publications_id": "RDBECOLIPRC03283"
    },
    "..."
  ],
  "externalCrossReferences": [
    {
      "externalCrossReferences_id": "RDBECOLIERC00004",
      "objectId": "P26647"
    },
    {
      "externalCrossReferences_id": "RDBECOLIERC00053",
      "objectId": "P26647"
    },
    "..."
  ],
  "genes_id": "RDBECOLIGNC01344",
  "internalComment": "; Source: EcoCyc",
  "isoelectricPoints": [
    9.76
  ],
  "locations": [
    "inner membrane"
  ],
  "molecularWeight": 27.453001,
  "molecularWeightsKd": [
    27.453001,
    25.0
  ],
  "name": "1-acylglycerol-3-phosphate <i>O</i>-acyltransferase PlsC"
}
```

## Main Relationships

- `genes_id` -> genes collection
- `terms[].terms_id` -> terms collection
- `citations[].publications_id` -> publications collection

## Related Pages

- [Core Database Collections](README.md)
- [Database Schema Overview](../database_schema_overview.md)
- [Data Volume](../data_volume.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
