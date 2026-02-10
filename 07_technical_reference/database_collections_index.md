# Database Collections Index

This index summarizes the primary MongoDB collections documented in the technical reference.

## Collections

| Collection | Approx. records | Main role | Documentation |
|---|---:|---|---|
| `additiveEvidences` | 681 | Additive evidence rules and integrated confidence logic | [Collection: Additive Evidences](collection_additive_evidences.md) |
| `evidences` | 95 | Evidence vocabulary and categories | [Collection: Evidences](collection_evidences.md) |
| `externalCrossReferences` | 57 | External source descriptors and URL templates | [Collection: External Cross References](collection_external_cross_references.md) |
| `regulatoryInteractions` | 6444 | Regulator -> regulated entity links | [Collection: Regulatory Interactions](collection_regulatory_interactions.md) |
| `genes` | 4747 | Gene objects and genomic features | [Collection: Genes](collection_genes.md) |
| `growthConditionContrasts` | 0 | Growth condition contrast records (empty in this snapshot) | [Collection: Growth Condition Contrasts](collection_growth_condition_contrasts.md) |
| `growthConditionPhrasesCatalogs` | 0 | Growth-condition phrase catalogs (empty in this snapshot) | [Collection: Growth Condition Phrases Catalogs](collection_growth_condition_phrases_catalogs.md) |
| `ontologies` | 1 | Ontology root/metadata records | [Collection: Ontologies](collection_ontologies.md) |
| `organisms` | 0 | Organism metadata records (empty in this snapshot) | [Collection: Organisms](collection_organisms.md) |
| `products` | 4664 | Product objects (proteins and related products) | [Collection: Products](collection_products.md) |
| `promoters` | 4057 | Promoter objects and TSS data | [Collection: Promoters](collection_promoters.md) |
| `publications` | 32225 | Publication link records | [Collection: Publications](collection_publications.md) |
| `transcriptionUnits` | 3766 | TU composition and links | [Collection: Transcription Units](collection_transcription_units.md) |
| `operons` | 2609 | Operon boundaries and orientation | [Collection: Operons](collection_operons.md) |
| `regulators` | 290 | Regulator/TF definitions and conformations | [Collection: Regulators](collection_regulators.md) |
| `regulatoryComplexes` | 228 | Regulatory complex objects and composition | [Collection: Regulatory Complexes](collection_regulatory_complexes.md) |
| `regulatoryContinuants` | 114 | Regulatory continuants (e.g., metabolites) | [Collection: Regulatory Continuants](collection_regulatory_continuants.md) |
| `regulatorySites` | 4632 | Regulatory binding site coordinates and sequence | [Collection: Regulatory Sites](collection_regulatory_sites.md) |
| `segments` | 18498 | Segment-level structural records | [Collection: Segments](collection_segments.md) |
| `sigmaFactors` | 7 | Sigma factor objects linked to promoters | [Collection: Sigma Factors](collection_sigma_factors.md) |
| `terminators` | 375 | Terminator objects and termination sites | [Collection: Terminators](collection_terminators.md) |
| `terms` | 5890 | Ontology terms and memberships | [Collection: Terms](collection_terms.md) |
| `transcriptionFactors` | 243 | TF-specific objects and conformations | [Collection: Transcription Factors](collection_transcription_factors.md) |

## Notes

- Record counts are based on the current JSON snapshot in `context/MongoDB/`.
- Counts should be refreshed when new data snapshots are integrated.

## Last Review

- Last updated: 2026-02-10
- Responsible area: RegulonDB Documentation and Governance Team
