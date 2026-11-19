<img src="../assets/icons/search.svg" alt="" width="48">

# Using Logical Operators in RegulonDB Search

The RegulonDB **search bar** accepts logical operators and exact phrases, so you can broaden or narrow a query without leaving the homepage.

The search bar itself shows two examples: `"Putative Membrane"` and `arac OR fimb`.

## Operators and Syntax

| Syntax | What it does | Example |
|:-------|:-------------|:--------|
| `"..."` | Searches for the **exact phrase** between quotation marks. | `"Putative Membrane"` |
| `OR` | Returns results that match **either** term. | `arac OR fimb` |
| `AND` | Returns results that match **both** terms. | `arabinose AND transporter` |
| `NOT` | **Excludes** results that contain the term after `NOT`. | `regulator NOT putative` |

Notes:

- Write operators in **uppercase** (`AND`, `OR`, `NOT`), as in the examples.
- Words written **without an operator are combined with `OR`**: `putative membrane` returns results that contain *putative* or *membrane*. To search both words together, use quotation marks (`"putative membrane"`) or `AND`.
- Search terms are not case-sensitive: `arac` finds `AraC` and `araC`.
- Results are grouped by object type (**Gene**, **Operon**, **Regulon**, **Sigmulon**, **GENSOR Unit**), with the number of matches in each group.

## Example Queries

| Query | Use it to |
|:------|:----------|
| `arac OR fimb` | Retrieve the entries of two regulators or genes in a single search. |
| `"Putative Membrane"` | Find objects whose description contains that exact phrase, instead of each word separately. |
| `arabinose AND transporter` | Narrow a broad keyword to the objects that also mention a second term. |
| `regulator NOT putative` | Leave out entries described as putative. |

## Tips

- Start with a simple term and add operators only if you get too many or too few results.
- Use quotation marks for multi-word names or descriptions.
- Use the result groups on the left side of the results page to jump to the object type you need.

## Related Content
- [Overview of Search and Navigation](search_overview.md)
- [Gene Search](gene_search.md)
- [Operon Search](operon_search.md)
- [Regulon Search](regulon_search.md)

## Last Review

- Last updated: 2026-11-18
- Maintained by: RegulonDB Team
