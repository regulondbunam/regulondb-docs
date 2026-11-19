# Standards and Ontologies Used in RegulonDB

This document summarizes the standards, ontologies, and controlled vocabularies adopted by **RegulonDB** to support metadata consistency, interoperability, and FAIR-aligned reuse.

## Scope

This page provides a public overview of the standards used to annotate, classify, and exchange RegulonDB data.

## 1. Gene Ontology (GO)

RegulonDB integrates **Gene Ontology** annotations to describe:

- **Molecular Function** (for example, ATP binding: GO:0005524).
- **Biological Process** (for example, transcriptional regulation pathways).
- **Cellular Component** (for example, cytoplasm: GO:0005737).

Gene product entries include GO terms linked to external references.

## 2. Evidence Code Ontology (ECO)

Curated objects in RegulonDB are associated with evidence codes aligned with ECO. Examples include:

- **EXP-IDA** (Inferred from Direct Assay).
- **EXP-IPI** (Inferred from Physical Interaction).
- **IC** (Inferred by Curator).

These evidence annotations provide traceability and support confidence assessment.

### Confidence Classification System

Promoters, regulatory interactions, binding sites, and transcription units are assigned confidence levels (weak, strong, confirmed) based on their supporting evidence. Current counts by confidence level are in [Data Volume](data_volume.md).

See the [Evidence Classification Document](https://regulondb.ccg.unam.mx/manual/help/evidenceclassification) for details.

Key references:

- Weiss, V., Medina-Rivera, A., Huerta, A. M., Santos-Zavaleta, A., Salgado, H., Morett, E., & Collado-Vides, J. (2013). Evidence classification of high-throughput protocols and confidence integration in RegulonDB. Database: The Journal of Biological Databases and Curation, bas059. [https://doi.org/10.1093/database/bas059](https://doi.org/10.1093/database/bas059)
- Lara, P., Gama-Castro, S., Salgado, H., Rioualen, C., Tierrafría, V. H., Muñiz-Rascado, L. J., Bonavides-Martínez, C., & Collado-Vides, J. (2024). Flexible gold standards for transcription factor regulatory interactions in *Escherichia coli* K-12: architecture of evidence types. Frontiers in Genetics, 15, 1353553. [https://doi.org/10.3389/fgene.2024.1353553](https://doi.org/10.3389/fgene.2024.1353553)

## 3. Microbial Conditions Ontology (MCO)

For datasets derived from experimental evidence (for example, ChIP-seq), metadata includes standardized growth conditions using **MCO**, such as:

- Organism: *Escherichia coli* K-12 MG1655.
- Medium: MOPS minimal medium + 0.2% glucose.
- Aeration: 95% N2 / 5% CO2.
- Temperature: 37 C.

This supports reproducibility of experimental context and integration with the original records in GEO (for example, sample GSM1010219).

Additional context:

- [Ontologies - Microbial Condition Ontology (MCO)](../01_search_browse/ontologies_mco.md)
- Tierrafría, V. H., Mejía-Almonte, C., Camacho-Zaragoza, J. M., Salgado, H., Alquicira, K., Ishida, C., Gama-Castro, S., & Collado-Vides, J. (2019). MCO: towards an ontology and unified vocabulary for a framework-based annotation of microbial growth conditions. Bioinformatics, 35(5), 856-864. [https://doi.org/10.1093/bioinformatics/bty689](https://doi.org/10.1093/bioinformatics/bty689)

## 4. File and Format Standards

- **Sequence formats**: FASTA and GenBank (for example, from gene pages).
- **Tabular datasets**: TSV files for regulatory interactions, regulators, networks, genes, and operon structure (see [Dataset Downloads](../02_data_access/dataset_downloads.md)).
- **Database dumps**: complete MongoDB dump of each release (see [Database Dumps](../02_data_access/database_dumps.md)).
- **Programmatic access**: JSON responses from the GraphQL API (see [API Access](../02_data_access/api_access.md)).

See also: [Data Access Portal](../02_data_access/README.md).

## 5. External Identifiers and Cross-References

Genes, products, and interactions are linked to persistent external identifiers, including:

- **UniProt**.
- **RefSeq**.
- **EcoCyc**, **InterPro**, **Pfam**, and related resources.

These links support interoperability and citation traceability.

## 6. Tools and Visualization Standards

- **Cytoscape-compatible** network exports for regulatory network analysis.
- **GENSOR Unit** visual representations for regulatory logic.
- Standard graphical and JSON outputs for downstream reuse.

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team

