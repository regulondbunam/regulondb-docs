<img src="../assets/icons/search.svg" alt="" width="48">

# Operon Search Guide

Welcome to the **Operon Search Guide** of RegulonDB.

This guide explains how to retrieve operon-related information using the **global search bar** or the **operon catalog** in the RegulonDB web interface.



## How Operon Search Works

RegulonDB uses a **unified search system** where operons can be queried using different fields. When a term matches an operon (by name, ID, associated gene, promoter, or transcription unit), the result will be listed under the **Operon** category.

| Field             | Description |
|:------------------|:------------|
| **Operon Name**      | Commonly accepted name (e.g., `lacZYA`, `araBAD`). |
| **RegulonDB ID**     | Unique operon identifier (e.g., `RDBECOLIOPC02880` for `lacZYA`). |
| **Promoter Name**    | Associated promoter names (e.g., `lacZp1`, `araBp`). |
| **Transcription Unit Name** | TU name in the format: `genes - promoter` (e.g., `lacZYA - lacZp1`). |
| **Gene Name**        | Any gene within the operon (e.g., `lacZ`, `araB`). |

You may use exact matches or combine fields using logical operators.

See [Using Logical Operators](logical_operators_search.md) for advanced search techniques.



## How to Perform an Operon Search

![](./assets/img/operon_search.png)

1. Go to the RegulonDB homepage.
2. Enter your query (e.g., `lacZYA` or `lacYA` or `lacZp1` or `lacY` ) in the **Search Bar**.
3. Press the **Search** button.
4. Review the categorized results.
5. Click on an operon name to access the detailed page.


![](./assets/img/operon_result.png)


## Information Available on an Operon Page

When selecting an operon from the results (e.g., `lacZYA`), you will find detailed, structured sections:

### Basic Operon Information

![](./assets/img/operon_summary.png)

- **Operon Summary**: 
	- **Operon Name**
	- **Genes included**
	- **Number of Promoters and Transcription Units**
	- **Genomic location** (coordinates and strand)



### Transcription Units (TUs)
Each operon may include one or more transcription units with this structure:

- TU Name: `genes - promoter`
- Genes included (e.g., `lacZYA`)
- Promoter (e.g., `lacZp1`)
- Transcription start site (TSS)
- Strand and distance to first gene


![](./assets/img/operon_tu.png)

Examples of TUs in the lac operon:

- `lacYA - lacYp`
- `lacZYA - lacZp1`, `lacZp2`, `lacZp3`, `lacZp4`

#### Promoter Details
- Promoter name and synonyms
- Sigma factor
- TSS and core promoter sequences (-10, -35 boxes)
- Confidence level and supporting evidence
- Downloadable sequence

#### Regulatory Interactions

![](./assets/img/operon_ris.png)

Table showing:
- Regulators (e.g., `LacI`, `CRP`)
- Role: activator (+), repressor (−), or dual (±)
- Position relative to promoter
- Binding site sequence

#### Terminators

![](./assets/img/operon_terminator.png)

- Type: rho-independent or dependent
- Coordinates and stem-loop structure
- Termination sequence

### Citations
All references supporting the annotations of the operon, promoters, and regulatory elements.

---

## Operon Search Examples

| Search Term                  | Expected Result                              |
|-----------------------------|----------------------------------------------|
| `lac`                       | lacZYA operon entry                          |
| `lacZp1`                    | Operon associated with promoter `lacZp1`     |
| `"lacZYA - lacZp3"`         | Operon from TU `lacZYA - lacZp3`             |
| `lacA`                      | Operon containing gene `lacA`                |
| `RDBECOLIOPC02880`          | Specific operon by RegulonDB ID (`lacZYA`)   |

Because words without an operator are combined with `OR`, avoid adding the word *operon* to your query; it would also return every object that mentions "operon". See [Using Logical Operators](logical_operators_search.md).

## Operon Catalog

To see the full list of operons as a table, click the **Operon** link below the search bar on the RegulonDB homepage.

![Links to the Genes, Operon, Regulon, Sigmulon, GENSOR Unit, and High Throughput catalogs below the search bar](./assets/img/home_catalog_links.png)

---

## Tips for Effective Operon Searches

- If you're unsure of the exact name, try searching by associated gene or promoter.
- Use the **Operon** link below the search bar to browse the full operon catalog.
- Combine keywords with logical operators to refine your query.

---

## Need Help?

If you have questions or need assistance with the operon search or navigation, please contact:

[regulondb@ccg.unam.mx](mailto:regulondb@ccg.unam.mx)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
