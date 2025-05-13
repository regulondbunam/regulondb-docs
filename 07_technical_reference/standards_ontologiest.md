# Standards and Ontologies Used in RegulonDB

This document outlines the community standards, ontologies, and controlled vocabularies adopted by **RegulonDB** to ensure metadata consistency, data interoperability, and alignment with FAIR principles.



## 1. Gene Ontology (GO)

RegulonDB integrates **Gene Ontology** annotations to describe:

- **Molecular Function**: e.g., ATP binding (GO:0005524), kinase activity  
- **Biological Process**: e.g., glycolate cycle, transcriptional regulation  
- **Cellular Component**: e.g., cytoplasm (GO:0005737)

Each gene product entry in RegulonDB includes a detailed list of GO terms, with links to GO databases. 


## 2. Evidence Code Ontology (ECO)
All curated objects in RegulonDB are associated with a defined **evidence code**, following the ECO standard. Examples include:

- **EXP-IDA** (Inferred from Direct Assay)  
- **EXP-IPI** (Inferred from Physical Interaction)  
- **IC** (Inferred by Curator)  

These evidence types are displayed for each object, providing traceability and enabling users to assess the **confidence level** of the annotations.


### Confidence Classification System
All regulatory objects (e.g., interactions, operons) are assigned a **confidence level** (e.g., weak, strong, confirmed), based on the supporting evidence codes.


see [Evidence Classification Document](https://regulondb.ccg.unam.mx/manual/help/evidenceclassification) for details.

Also check the reference:

- Weiss, V., Medina-Rivera, A., Huerta, A. M., Santos-Zavaleta, A., Salgado, H., Morett, E., & Collado-Vides, J. (2013). Evidence classification of high-throughput protocols and confidence integration in RegulonDB. Database : the journal of biological databases and curation, 2013, bas059. [https://doi.org/10.1093/database/bas059](https://doi.org/10.1093/database/bas059)


## 3. Microbial Conditions Ontology (MCO)
For datasets derived from experimental evidence (e.g., ChIP-seq), metadata includes standardized conditions using the **Microbial Conditions Ontology**, such as:

- Organism: *Escherichia coli* K-12 MG1655  
- Medium: MOPS minimal medium + 0.2% glucose  
- Aeration: 95% N₂ / 5% CO₂  
- Temperature: 37°C  

This allows integration with GEO datasets (e.g., GSM1010219) and reproducibility of experimental context.

For details see the cite:

- Tierrafría, V. H., Mejía-Almonte, C., Camacho-Zaragoza, J. M., Salgado, H., Alquicira, K., Ishida, C., Gama-Castro, S., & Collado-Vides, J. (2019). MCO: towards an ontology and unified vocabulary for a framework-based annotation of microbial growth conditions. Bioinformatics (Oxford, England), 35(5), 856–864. [https://doi.org/10.1093/bioinformatics/bty689](https://doi.org/10.1093/bioinformatics/bty689)


## 4. File and Format Standards

- **Sequence Formats**: FASTA and GenBank are available for all genes and transcription units.  
- **Tabular Downloads**: TSV and CSV formats are provided across gene, regulatory interaction, and network datasets.  
- **Data Dumps**: Available for different objects as Regulatory Interactions (RISet), Regulators (TFSet), promoters, etc.



## 5. External Identifiers and Cross-References

Each gene, product, or interaction object in RegulonDB is linked to external databases using persistent identifiers:

- **UniProt** (e.g., P76052)  
- **RefSeq** (e.g., NP_415853)  
- **EcoCyc**, **InterPro**, **Pfam**, etc.


These links support interoperability and citation tracking.



## 6. Tools and Visualization Standards

- **Cytoscape-compatible** network files for visualizing gene regulatory networks.  
- **Gensor Unit diagrams** to represent complex transcriptional regulatory cascades.  
- Downloads in standard graphical and JSON formats to support external analysis.


