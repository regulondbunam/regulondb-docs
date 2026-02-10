# Database Schema Overview

This page provides a public technical overview of the RegulonDB MongoDB-oriented data model using the exported JSON collections available in this repository.

## Scope

- Collection-level structure and relationships.
- Identifier conventions used across objects.
- Core entities for transcriptional regulation data.

## Data Source Used for This Overview

- Path: `context/MongoDB/`
- Dataset prefix: `regulondbmultigenomic.*.json`

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

## Related Pages

- [Database Collections Index](database_collections_index.md)
- [Collection: Genes](collection_genes.md)
- [Collection: Regulators](collection_regulators.md)
- [Collection: Regulatory Interactions](collection_regulatory_interactions.md)
- [Collection: Operons](collection_operons.md)
- [Collection: Promoters](collection_promoters.md)
- [Collection: Transcription Units](collection_transcription_units.md)
- [Collection: Evidences](collection_evidences.md)

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
