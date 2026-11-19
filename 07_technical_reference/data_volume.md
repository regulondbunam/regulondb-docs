# Data Volume

This page reports the volume of curated data in RegulonDB, by object type and confidence level. Counts correspond to release **14.5.1** (2026-11-11) and are taken from the release statistics stored in the release database (`databaseInfo` collection). The counts of each release are also published in its release note (see the [release history](https://regulondb.ccg.unam.mx/summaryHistory)).

## Curated Objects by Confidence Level

Confidence levels (weak, strong, confirmed) are assigned from the supporting evidence; see the [Evidence Classification Document](https://regulondb.ccg.unam.mx/manual/help/evidenceclassification).

| Object | Total | Weak | Strong | Confirmed | With evidence |
|---|---:|---:|---:|---:|---:|
| Regulatory interactions | 6,460 | 2,196 | 3,121 | 1,101 | 6,017 |
| Regulator binding sites | 4,647 | 2,341 | 1,513 | 422 | 4,294 |
| Promoters | 4,057 | 2,670 | 1,271 | 77 | 4,056 |
| Transcription units | 3,767 | 2,590 | 730 | 36 | 3,367 |
| Transcription factors | 243 | 149 | 87 | 0 | 236 |
| Regulatory complexes (TF conformations) | 228 | 99 | 67 | 0 | 170 |
| Sigma factors | 7 | 3 | 1 | 0 | 4 |

## Other Objects

| Object | Total |
|---|---:|
| Genes | 4,748 |
| Gene products | 4,664 (4,471 polypeptides, 109 RNAs, 84 small RNAs) |
| Operons | 2,605 |
| Terminators | 375 |
| Regulons | 293 (243 transcription factors, 49 small RNAs, 1 regulatory continuant) |
| GENSOR Units | 240 |
| Regulatory continuants (effectors and metabolites) | 114 |
| Motifs | 30,339 |
| Genomic segments | 18,524 |
| Ontology terms (MCO) | 5,656 |
| Publications | 17,692 |
| Evidence types (catalog) | 115 |

## Links to External Resources

| Indicator | Total |
|---|---:|
| Cross-references from RegulonDB objects to external records | 32,475 |
| Links to external database records | 132,921 |

Links to external database records by source: EcoCyc 59,395; RefSeq 8,943; ASAP 4,458; EcoliWiki 4,433; UniProt 4,407; other sources 51,285. See [Relationships with External Data Resources](db_relationships.md).

## High-Throughput Data

The high-throughput (HT) collections of release 14.5.1 contain 2,445 datasets, with 3,142 transcription factor binding records, 20,990 peaks, 68,044 transcription start sites, 5,326 transcription termination sites, 12,329 transcription units, and 8,606,088 gene expression values. See [Datamarts (Release Dump)](datamarts/README.md).

## Related Pages

- [Database Schema Overview](database_schema_overview.md)
- [Core Database Collections](core_collections/README.md)
- [Version History](../05_releases_updates/version_history.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
