# RegulonDB Documentation Style Guide

This guide describes how documentation pages are written in markdown and how the documentation viewer of the RegulonDB website presents them with the RegulonDB palette. Authors only follow a few markdown conventions; colors and layout come from the style sheet and the viewer.

## Scope

The style applies to the root `README.md` and to the sections `00_about_policies`, `01_search_browse`, `02_data_access`, `04_curation/glossary`, `04_curation/evidenceclassification.md`, `05_releases_updates`, and `07_technical_reference`. The icons `tools.svg` and `tutorials.svg` are ready for the sections 03 and 06 when they are documented.

## For Authors

### Page Structure

Each page starts with the icon of its section, followed by the page title:

```markdown
<img src="../assets/icons/search.svg" alt="" width="48">

# Gene Search
```

The path to the icon is relative to the page (`../` for pages in a section folder, `../../` for pages one level deeper).

| Section | Icon |
|---|---|
| Home (root `README.md`) | `assets/icons/home.svg` |
| 00 About and Policies | `assets/icons/about.svg` |
| 01 Search and Browse | `assets/icons/search.svg` |
| 02 Data Access | `assets/icons/data_access.svg` |
| 04 Curation (glossary) | `assets/icons/curation.svg` |
| 05 Releases and Updates | `assets/icons/releases.svg` |
| 07 Technical Reference | `assets/icons/technical.svg` |

Use only one icon per page, before the title. Do not use emoji in titles or text.

### Notes

Write notes as a block quote that starts with a bold label:

```markdown
> **Note.** Logical operators combine several search terms.

> **Important.** This command removes all Docker images on your computer.
```

Use **Note** for complementary information and **Important** for warnings.

### Related Content

End each page with a list of related pages, before the review block:

```markdown
## Related Content

- [Gene Search](gene_search.md)
- [Operon Search](operon_search.md)

## Last Review

- Last updated: YYYY-MM-DD
- Maintained by: RegulonDB Team
```

### Other Conventions

- Titles in Title Case; one `#` title per page.
- Tables, code blocks, and images in standard markdown.
- Figures stored next to the page (for example, in an `images/` folder) and referenced with relative paths.

## For the Web Team

The GitHub Pages site of this repository already applies these rules in `_layouts/default.html`; the RegulonDB web application can follow the same logic.

The viewer converts markdown to HTML and then applies [`assets/css/regulondb-docs.css`](css/regulondb-docs.css).

### Palette

| Use | Color |
|---|---|
| Navigation band, titles, links, icons | `#32617D` |
| Dark text on tints, subtitles | `#1F3D4F` |
| Note border | `#3F7AA0` |
| Table header | `#72A6CA` |
| Section name (eyebrow) | `#C99A06` |
| Important notes, primary buttons | `#C93A20` |
| Grays | `#3A3A3A`, `#6B6B6B`, `#9B9B9B`, `#D5D5D5`, `#F3F3F3` |

### Rendering Rules

1. Wrap the rendered page in `<article class="rdb-doc">`.
2. **Header.** If the page starts with an icon image followed by an `h1`, move both into a header and add the section name (taken from `SUMMARY.md`):

   ```html
   <header class="rdb-doc-header">
     <img src="…/assets/icons/search.svg" alt="">
     <div>
       <div class="rdb-eyebrow">Search and Browse</div>
       <h1>Gene Search</h1>
     </div>
   </header>
   <div class="rdb-doc-body"> … rest of the page … </div>
   ```

3. **Important notes.** Add the class `rdb-important` to the paragraph that starts with `<strong>Important.</strong>`; the style sheet colors its block quote.
4. **Related content.** Wrap the `h2` "Related Content" and the list that follows it in `<div class="rdb-related">`.
5. Pages without an icon are shown with the same style, without the header.

Without the viewer (for example, on GitHub), pages show the icon above the title and the rest as plain markdown.

### Icons

Section icons are SVG files in `assets/icons/`: a white glyph on a `#32617D` circle, 48 × 48 px. The glyphs come from [Tabler Icons](https://tabler.io/icons) (MIT License); each file names its glyph in a comment. To add a section icon, copy an existing file and replace the glyph paths.

## Last Review

- Last updated: 2026-11-19
- Maintained by: RegulonDB Team
