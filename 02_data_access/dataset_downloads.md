# Downloadable Datasets Guide

This guide explains how to access and download public datasets from RegulonDB.

## Entry Point

- Main datasets page: [https://regulondb.ccg.unam.mx/datasets](https://regulondb.ccg.unam.mx/datasets)

## What You Can Download

The **Downloadable Experimental Datasets** page groups the files as follows:

| Group | File | Description |
|:------|:-----|:------------|
| Regulatory interaction | `RISet` | Regulatory interactions between a regulator and its regulated entity (promoter, gene, or transcription unit). |
| | `TF-RISet` | Regulatory interactions between a transcription factor and its regulated entity (subset of `RISet`). |
| Regulator | `RegulatorSet` | Regulators and their conformations (transcription factors, small RNAs, and ppGpp). |
| | `TFSet` | Transcription factors and their conformations (subset of `RegulatorSet`). |
| Regulatory network | `NetworkRegulatorGene` | Regulator → regulated gene interactions. |
| | `NetworkRegulatorTU` | Regulator → regulated transcription unit interactions. |
| | `NetworkRegulatorRegulator` | Regulator → regulated regulator interactions. |
| | `NetworkSigmaGene` | Sigma factor → regulated gene interactions. |
| | `NetworkSigmaTU` | Sigma factor → regulated transcription unit interactions. |
| | `NetworkRegulatorConfGene` | Active conformation of the regulator → regulated gene interactions. |
| Gene | `GeneProductSet` | Genes and information about their products. |
| | `Gene_sequence` | DNA sequence of the genes. |
| | `GeneProductAllIdentifiersSet` | Genes and products with synonyms and identifiers in other databases, for mapping and cross-referencing. |
| Operon structure | `OperonSet` | Operons and their genes. |
| | `TUSet` | Transcription units with information on operon, promoter, and terminator. |
| | `PromoterSet` | Promoters and their first transcribed genes. |
| | `TerminatorSet` | Terminators. |
| | `UTR_5_3_sequence` | Untranslated transcription unit regions (5' and 3' UTRs). |
| | `TuPromOperonTFSet` | Transcription units with information on operon, promoter, terminator, and transcription factors. |
| Evidence | `EvidenceSet` | Evidence catalog that supports the data. |
| | `AdditiveEvidenceSet` | Additive evidence catalog. |

## Options for Each File

Each file has up to three options in the **Options** column:

- **Download** (arrow icon): downloads the complete file.
- **Browse & Filter** (magnifying-glass icon): opens the file as an interactive table where you can filter columns and download the filtered subset in TSV format.
- **Confidence Level Calculator** (flask icon, available for `RISet` and `TF-RISet`): recalculates the confidence level of each interaction after excluding the evidence types you choose. See [Creating Gold Standard Datasets](gold_standard_guide_en.md).

## Download Workflow

1. Open the datasets page.
2. Locate the group and the file you need.
3. Click **Download** to get the complete file, or **Browse & Filter** to export a subset.
4. For regulatory interactions, optionally use the **Confidence Level Calculator** to build custom high-confidence subsets.

## Recommended Usage

- Use full downloads for reproducible local analysis.
- Use filtered exports when building focused subsets.
- Record the dataset name, RegulonDB release (for example, v14.5.1), download date, and source URL for traceability (see [How to Cite RegulonDB](../00_about_policies/how_to_cite.md)).

## Related Pages

- [Creating Gold Standard Datasets](gold_standard_guide_en.md)
- [Database Dumps](database_dumps.md)
- [API Access](api_access.md)
- [How to Cite RegulonDB](../00_about_policies/how_to_cite.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
