# Core Database Collections

This index summarizes the **core collections** (database `regulondbmultigenomic`): one collection per type of biological object. They are the source from which the datamarts used by the web interface and the API are generated; for the collections included in the release download, see [Datamarts (Release Dump)](../datamarts/README.md).

Counts and field structures correspond to the export of release **14.5.1** (May 2026) and to the JSON Schemas used to validate each collection.

## Collections

| Collection | Documentation | Documents | Main role |
|---|---|---:|---|
| `additiveEvidences` | [Additive Evidences](collection_additive_evidences.md) | 353 | Stores additive evidence rules used to derive integrated confidence evidence from combinations of base evidence types. |
| `evidences` | [Evidences](collection_evidences.md) | 115 | Defines evidence vocabulary used to support curation confidence and provenance across RegulonDB objects. |
| `externalCrossReferences` | [External Cross References](collection_external_cross_references.md) | 57 | Defines external resource descriptors used by many collections for interoperable cross-links. |
| `genes` | [Genes](collection_genes.md) | 4,748 | Stores core gene objects with genomic coordinates, sequence, and cross-references. |
| `growthConditionContrasts` | [Growth Condition Contrasts](collection_growth_condition_contrasts.md) | not exported | Stores contrasts/comparisons between growth conditions when available. |
| `growthConditionPhrasesCatalogs` | [Growth Condition Phrases Catalogs](collection_growth_condition_phrases_catalogs.md) | not exported | Intended to store cataloged phrase resources related to growth condition annotation. |
| `motifs` | [Motifs](collection_motifs.md) | 30,339 | Stores motifs and features of gene products (for example, signal sequences and domains), with their class, their position in the product sequence, and the product they belong to. |
| `ontologies` | [Ontologies](collection_ontologies.md) | 1 | Stores ontology roots/metadata used by ontology-linked terms. |
| `operons` | [Operons](collection_operons.md) | 2,605 | Stores operon objects with genomic range and strand orientation. |
| `organisms` | [Organisms](collection_organisms.md) | 1 | Intended to store organism-level metadata referenced by `organisms_id` fields. |
| `products` | [Products](collection_products.md) | 4,664 | Stores gene products (proteins and other functional products), including biochemical attributes and cross-references. |
| `promoters` | [Promoters](collection_promoters.md) | 4,057 | Stores promoter objects, sigma-factor association, sequence boxes, and transcription start site (TSS) information. |
| `publications` | [Publications](collection_publications.md) | 32,475 | Stores publication records referenced by citations across curated objects. |
| `regulators` | [Regulators](collection_regulators.md) | 293 | Defines regulator entities (including transcription factors), with confidence, conformations, and evidence-linked citations. |
| `regulatoryComplexes` | [Regulatory Complexes](collection_regulatory_complexes.md) | 228 | Stores regulatory or functional complexes composed of products, including stoichiometry and contextual notes. |
| `regulatoryContinuants` | [Regulatory Continuants](collection_regulatory_continuants.md) | 114 | Stores regulatory continuants (for example metabolites and small molecules) linked to regulation context. |
| `regulatoryInteractions` | [Regulatory Interactions](collection_regulatory_interactions.md) | 6,460 | Represents regulatory links between a regulator and a regulated entity (a promoter, a gene, or a transcription unit), including function, confidence level, and supporting citations. |
| `regulatorySites` | [Regulatory Sites](collection_regulatory_sites.md) | 4,647 | Stores regulatory binding sites with genomic coordinates, sequence, and confidence/citation support. |
| `segments` | [Segments](collection_segments.md) | 18,524 | Stores genomic segment objects linked to parent classes (for example terminators or mRNA-related segments). |
| `sequences` | [Sequences](collection_sequences.md) | 27 | Stores the counters used to generate RegulonDB identifiers: one document per object type (for example, `genes`, `promoters`, `operons`), with the organism, class and subclass acronyms that form the identifier prefix and the last value assigned. |
| `sigmaFactors` | [Sigma Factors](collection_sigma_factors.md) | 7 | Stores sigma factor objects used in promoter recognition and transcription initiation context. |
| `terminators` | [Terminators](collection_terminators.md) | 375 | Stores transcription terminator objects, including class, sequence, and termination-site coordinates. |
| `terms` | [Terms](collection_terms.md) | 5,656 | Stores ontology terms and their membership links to biological objects. |
| `transcriptionFactors` | [Transcription Factors](collection_transcription_factors.md) | 243 | Stores transcription-factor specific objects, including active/inactive conformations and functional properties. |
| `transcriptionUnits` | [Transcription Units](collection_transcription_units.md) | 3,767 | Represents transcription units (TUs) and links to promoters, operons, genes, and terminators. |

## Notes

- `growthConditionContrasts` and `growthConditionPhrasesCatalogs` are defined in the validation schemas but have no data in release 14.5.1. The schemas also define `regulatoryModules`, `rfams`, and `shineDalgarnos`, which are not part of the release export.
- `publications` contains 32,475 records; the release statistics report 17,692 publications (see [Data Volume](../data_volume.md)).
- Identifiers follow the pattern `RDB` + organism, class, and subclass acronyms + a five-digit number (for example, `RDBECOLIGNC00001`), defined in the validation schemas; the counters used to assign them are stored in the [`sequences`](collection_sequences.md) collection.

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
