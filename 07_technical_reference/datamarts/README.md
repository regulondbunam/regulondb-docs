# Datamarts (Release Dump Collections)

The datamarts are view-like collections aligned with the RegulonDB web interface. The web application and the GraphQL API read from them, and they are the collections included in the release download (MongoDB dump). They are generated at each release from the **core collections** (database `regulondbmultigenomic`); see [Database Schema Overview](../database_schema_overview.md).

Counts and structures below were obtained from the dump of release **14.5.1** (2026-11-11).

## Database `regulondbdatamarts` (curated knowledge)

| Collection | Datamart | Documents | Size | Purpose |
|---|---|---:|---:|---|
| `databaseInfo` | [Database Info](dm_database_info.md) | 59 | 222.3 KB | Metadata of each RegulonDB release: version, release date, EcoCyc and genome versions, release note, content statistics, and the route of the release download. |
| `dnaFeatures` | [DNA Features](dm_dna_features.md) | 15,091 | 25.5 MB | Genomic features with coordinates and drawing attributes (label, colors, line style, tooltip) used to draw genomic regions. |
| `downloadableFilesDatamart` | [Downloadable Files](dm_downloadable_files_datamart.md) | 24 | 28.5 MB | The downloadable datasets of the **Downloadable Experimental Datasets** page (for example, `RISet`, `TF-RISet`, `GeneProductSet`): file name, title, description, column details, license header, RegulonDB version, and the file content. |
| `evidencesDatamart` | [Evidences](dm_evidences_datamart.md) | 115 | 55.1 KB | Evidence catalog used in the interface (evidence codes, names, types, and categories). |
| `geneCoexpressions` | [Gene Coexpressions](dm_gene_coexpressions.md) | 9,316,077 | 2.0 GB | Pairwise gene coexpression values: gene pairs with their coexpression rank and display color. |
| `geneDatamart` | [Gene](dm_gene_datamart.md) | 4,748 | 132.7 MB | One document per gene with everything shown on the gene page: gene data, products, regulation (operons, promoters, regulators), organism, and citations. |
| `gensorUnitDatamart` | [GENSOR Unit](dm_gensor_unit_datamart.md) | 240 | 12.0 MB | One document per GENSOR Unit (genetic sensory response unit): the unit description and its reactions, with the total number of components and reactions. |
| `growthCondition` | [Growth Condition](dm_growth_condition.md) | 0 | 0 B | Growth conditions of regulatory interactions. |
| `listPage` | [List Page](dm_list_page.md) | 7,650 | 1.2 MB | Lightweight list of objects (name, synonyms, encoded genes, product names) for the catalogs. |
| `mcoTree` | [MCO Tree](dm_mco_tree.md) | 5,656 | 6.1 MB | Terms of the Microbial Condition Ontology (MCO) organized as a tree. |
| `operonDatamart` | [Operon](dm_operon_datamart.md) | 2,605 | 66.8 MB | One document per operon with everything shown on the operon page: operon data, transcription units, promoters, terminators, regulatory interactions, and citations. |
| `overviews` | [Overviews](dm_overviews.md) | 0 | 0 B | Summary distributions of RegulonDB objects. |
| `phrases` | [Phrases](dm_phrases.md) | 0 | 0 B | Curated phrases (text evidence) associated with objects. |
| `recentQueriesDM` | [Recent Queries](dm_recent_queries.md) | 4 | 505 B | Recently used queries. |
| `regulatoryNetworkDatamart` | [Regulatory Network](dm_regulatory_network_datamart.md) | 5,038 | 54.6 MB | Nodes of the regulatory network (genes, transcription factors, and other regulators) with their incoming (`indegree`) and outgoing (`outdegree`) regulatory links. |
| `regulonDatamart` | [Regulon](dm_regulon_datamart.md) | 290 | 150.2 MB | One document per regulon with everything shown on the regulon page: regulator, regulated objects (genes, operons, transcription units), regulatory interactions, summary counts, GO terms, and citations. |
| `sigmulonDatamart` | [Sigmulon](dm_sigmulon_datamart.md) | 7 | 9.2 MB | One document per sigma factor with its sigmulon: sigma factor data, transcribed promoters, summary statistics, and citations. |
| `srnaDatamart` | [Small RNA](dm_srna_datamart.md) | 0 | 0 B | Small RNA regulators. |

## Database `regulondbht` (high-throughput data)

| Collection | Datamart | Documents | Size | Purpose |
|---|---|---:|---:|---|
| `authorsData` | [HT Authors Data](ht_authors_data.md) | 573 | 36.4 MB | Data tables as reported by the authors of each high-throughput (HT) dataset. |
| `dataset` | [HT Dataset](ht_dataset.md) | 2,445 | 3.6 MB | Metadata of each high-throughput (HT) dataset: source, publication, sample, experimental conditions, and processing. |
| `geneExpression` | [HT Gene Expression](ht_gene_expression.md) | 8,606,088 | 2.6 GB | Gene expression values per HT dataset and gene. |
| `htDatasetCollections` | [HT Dataset Collections](ht_dataset_collections.md) | 0 | 0 B | Grouping of HT datasets into collections. |
| `metadata` | [HT Metadata](ht_metadata.md) | 12 | 22.1 KB | General metadata and release information of the HT collections by dataset type. |
| `nlpGrowthConditions` | [HT NLP Growth Conditions](ht_nlp_growth_conditions.md) | 1,576 | 1.7 MB | Growth conditions of HT datasets extracted with natural language processing (NLP). |
| `peaks` | [HT Peaks](ht_peaks.md) | 20,990 | 14.7 MB | Peaks from ChIP-type HT experiments, with coordinates and scores. |
| `tfBinding` | [HT TF Binding](ht_tf_binding.md) | 3,142 | 2.6 MB | Transcription factor binding sites identified in HT experiments. |
| `transcriptionStartSite` | [HT Transcription Start Sites](ht_transcription_start_site.md) | 68,044 | 49.3 MB | Transcription start sites (TSS) identified in HT experiments. |
| `transcriptionTerminationSite` | [HT Transcription Termination Sites](ht_transcription_termination_site.md) | 5,326 | 3.8 MB | Transcription termination sites (TTS) identified in HT experiments. |
| `transcriptionUnit` | [HT Transcription Units](ht_transcription_unit.md) | 12,329 | 4.9 MB | Transcription units identified in HT experiments. |

## Notes

- Collections marked as empty (`growthCondition`, `overviews`, `phrases`, `srnaDatamart`, `htDatasetCollections`) have no documents in release 14.5.1.
- The "Source (core collections)" section of each page is an initial mapping that must be validated by the software team.

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
