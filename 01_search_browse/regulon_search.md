# 🧬 Regulon Search Guide

Welcome to the **Regulon Search Guide** of RegulonDB.

This guide explains how to retrieve regulon-related information using the **global search bar** and the **Regulon catalog** in the RegulonDB web interface.



## 📚 How Regulon Search Works

RegulonDB uses a **unified search system** where regulons can be queried using different fields. When a term matches a regulon, the result appears under the **Regulon** category.

| Field | Description |
|:------|:------------|
| **TF Name** | Name of the transcription factor regulating the regulon (e.g., `AraC`, `CRP`). |
| **TF Synonyms** | Alternative names used in literature or other resources. |
| **TF ID** | RegulonDB identifier of the transcription factor/regulator entry. |
| **Gene Name (TF coding gene)** | Name of the gene that encodes the transcription factor (e.g., `araC`). |

You can search using full names or partial matches.



## 🔎 How to Perform a Regulon Search

1. Open the RegulonDB homepage.
2. Enter a query in the **Search Bar** (for example, TF name, synonym, TF ID, or coding gene name).
3. Click **Search**.
4. Review categorized results and locate the **Regulon** section.
5. Click the regulon entry to open the detailed regulon page.

The unified result view may also show related matches in **Gene**, **Operon**, **Sigmulon**, and **GENSOR Unit** categories.



## 📋 Regulon Catalog Navigation

Below the global search bar, use the **Regulon** link to open the catalog of regulons.

In the regulon catalog table, you can:

- Browse all available regulons.
- Filter by regulon name.
- Filter numeric ranges (regulated genes, operons, transcription units, regulatory interactions, binding sites).
- Click a regulon name to navigate to its detailed page.
- Use table actions such as **Download** and **Hide/View Columns**.



## 📄 Information Available on a Regulon Page

When you open a regulon entry, you will find structured sections such as:

### 🧬 Regulator Section

- Regulator name and type.
- Synonyms.
- Encoded-by gene and associated operon.
- Summary description of the regulator.
- Conformations (if available).
- References and evidence.

### 🧩 Regulon Summary Section

- Network view of regulated entities.
- Counts and tables of:
  - Regulated genes
  - Regulated operons
  - Regulated transcription units

### ⚙️ Regulatory Interactions Section

- Detailed interaction table including:
  - Active conformation name
  - Function (activator/repressor/dual)
  - Regulated entity name and type
  - Distance to first gene/promoter
  - Regulated genes
  - RBS coordinates (when available)

### 🧬 GO Terms of Regulated Genes

- Cellular Component
- Molecular Function
- Biological Process

### 📚 All References and Evidence

- Curated literature references supporting regulon annotation.
- Linked evidence labels and traceability.



## 🧪 Regulon Search Examples

| Search Term | Expected Result |
|:------------|:----------------|
| `AraC` | Regulon entry controlled by AraC. |
| `RDBECOLITFC00022` | Direct match to a specific TF/regulon record. |
| `araC` | Regulon associated with the gene encoding AraC. |
| `XylR` | Regulon controlled by XylR. |



## 🛠️ Tips for Effective Regulon Searches

- If no direct regulon result appears, check the **Gene** result and navigate from regulator-related links.
- Use the **Regulon catalog** for discovery when exact naming is uncertain.
- Combine text search with table filters in the catalog to narrow large result sets.
- Use download options from tables to export subsets for external analysis.



## 📬 Need Help?

If you have questions or need assistance with regulon search or navigation, please contact:

📧 [regulondb@ccg.unam.mx](mailto:regulondb@ccg.unam.mx)
