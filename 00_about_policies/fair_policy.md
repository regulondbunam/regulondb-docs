# 📖 FAIR Data Policy

_Last updated: [Insert Date]_

---

## 1. Introduction

At RegulonDB, we are committed to the principles of FAIR data management:  
**Findable, Accessible, Interoperable, and Reusable**.

This policy outlines how we implement FAIR principles across our curated datasets, metadata, web services, and documentation.

Our goal is to maximize the value, usability, and sustainability of transcriptional regulation data for the scientific community.

---

## 2. Commitment to FAIR Principles

We ensure that all data and metadata managed by RegulonDB adhere to the following:

- **Findable:**
  - All curated entities (genes, promoters, operons, regulators, regulatory interactions, etc.) are indexed and searchable through our web interface and APIs.
  - Persistent and unique identifiers (IDs) are assigned to each biological entity.
  - Metadata descriptions are standardized and available.

- **Accessible:**
  - Datasets, APIs, and database dumps are openly available through our [Data Access Portal](../02_data_access/README.md).
  - No authentication is required for basic data access.
  - Programmatic access is enabled via RESTful and GraphQL APIs.

- **Interoperable:**
  - Data is structured using standard ontologies such as the [Microbial Condition Ontology (MCO)](../01_search_browse/ontologies_mco.md).
  - Metadata and schemas are designed for compatibility with external systems (e.g., BioCyc, EcoCyc, UniProt).
  - Common data formats (JSON, CSV, MongoDB dumps) are provided.

- **Reusable:**
  - Clear licensing terms are published ([License](license.md)).
  - Full provenance is documented, including sources and evidence codes.
  - Detailed curation protocols are available in the [Curation Manual](../04_curation_manual/README.md).

---

## 3. Data Formats and Accessibility

We offer access to RegulonDB content via:

- **Web Portal:** Interactive search, browse, and visualization.
- **API Access:** GraphQL and REST endpoints for programmatic querying.
- **Downloadable Datasets:** CSV, JSON files, and full MongoDB database dumps.
- **Dockerized Instances:** For local deployment and offline analysis.

All resources are versioned and publicly released with detailed changelogs.

---

## 4. Metadata Standards

RegulonDB metadata complies with:

- Minimal information requirements for transcriptional regulation.
- Ontology-based annotations using MCO.
- Evidence classification standards based on experimental validation and computational inference.

---

## 5. Reuse and Licensing

Unless otherwise specified, RegulonDB data is distributed under a [Creative Commons Attribution-ShareAlike 4.0 International License (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/).

Users are encouraged to reuse, adapt, and integrate the data, provided appropriate credit is given to RegulonDB and its contributors.

Proper citation guidelines are provided in our [How to Cite](how_to_cite.md) page.

---

## 6. Continuous Improvement

We are committed to regularly reviewing and updating our data policies, workflows, and technological platforms to better align with evolving FAIR practices and community standards.

Feedback from users is welcome and actively encouraged.

---

## 7. Contact Information

If you have questions, suggestions, or require assistance regarding our FAIR implementation, please contact us at:

📧 [regulondb@ccg.unam.mx](mailto:regulondb@ccg.unam.mx)

Thank you for supporting open, FAIR data science! 🌟

---
