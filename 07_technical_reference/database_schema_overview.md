<img src="../assets/icons/technical.svg" alt="" width="48">

# Database Schema Overview

This page provides a public technical overview of the RegulonDB MongoDB-oriented data model. The collection pages in this section describe the **core collections**, from which the datamarts used by the web interface and the API are generated.

## Two Data Layers: Core Collections and Datamarts

RegulonDB data are organized in two layers:

| Layer | Database | What it contains | Used by |
|:------|:---------|:-----------------|:--------|
| **Core collections** | `regulondbmultigenomic` | One collection per biological object (for example, `genes`, `operons`, `promoters`, `regulatoryInteractions`, `evidences`). This is the source database. | Generation of the datamarts. |
| **Datamarts** | `regulondbdatamarts` (and `regulondbht` for high-throughput data) | View-like collections aligned with the web interface (for example, `geneDatamart`, `operonDatamart`, `regulonDatamart`), generated from the core collections. | The web application and the GraphQL API. |

The datamarts are documented in [Datamarts (Release Dump)](datamarts/README.md).

## Scope

- Collection-level structure and relationships.
- Identifier conventions used across objects.
- Core entities for transcriptional regulation data.

## Data Source Used for This Overview

- Core collections: JSON export of `regulondbmultigenomic` for release 14.5.1, with the JSON Schemas used to validate each collection.
- Datamarts: MongoDB dump of release 14.5.1 (`regulondbdatamarts`, `regulondbht`).

## Identifier Conventions

RegulonDB objects use stable internal identifiers in `_id` fields, for example:

- Gene: `RDBECOLIGNC...`
- Regulator/TF: `RDBECOLITFC...`
- Regulatory interaction: `RDBECOLIRIC...`
- Promoter: `RDBECOLIPMC...`
- Operon: `RDBECOLIOPC...`
- Transcription unit: `RDBECOLITUC...`
- Evidence: `RDBECOLIEVC...`

Relationships are represented through fields like:

- `*_id` (single reference)
- `*_ids` (list reference)
- embedded link objects containing `_id`, `name`, and `type`

## Core Collections (Phase 1)

- `genes`
- `regulators`
- `regulatoryInteractions`
- `operons`
- `promoters`
- `transcriptionUnits`
- `evidences`

## Relationship Pattern (High Level)

- `regulatoryInteractions` links regulators to regulated entities.
- `promoters` reference sigma factors and transcription start sites.
- `transcriptionUnits` link promoters, operons, genes, and terminators.
- `operons` describe genomic ranges and strand orientation.
- `regulators` include conformations and citations.
- `evidences` define evidence codes and categories used across annotations.

## Related Content
- [Database Collections Index](core_collections/README.md)
- [Collection: Genes](core_collections/collection_genes.md)
- [Collection: Regulators](core_collections/collection_regulators.md)
- [Collection: Regulatory Interactions](core_collections/collection_regulatory_interactions.md)
- [Collection: Operons](core_collections/collection_operons.md)
- [Collection: Promoters](core_collections/collection_promoters.md)
- [Collection: Transcription Units](core_collections/collection_transcription_units.md)
- [Collection: Evidences](core_collections/collection_evidences.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
