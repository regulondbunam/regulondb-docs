# Impact Stories

This page summarizes public impact cases that illustrate how RegulonDB accelerates research, enables reproducible analysis, and supports the broader life sciences community.

## Scope

- Public-facing evidence of scientific and technical impact.
- Narrative format supported by citable publications or traceable outputs.
- Complementary to citation lists and release documentation.

## Story 1: Accelerating Experimental Discovery

### Context
Experimental studies in *E. coli* need trusted reference knowledge, both to design new experiments and to interpret their results.

### RegulonDB Contribution
RegulonDB provides curated binding sites, promoters, and terminators, each supported by evidence, that researchers reuse directly in experimental design and genome annotation.

### Examples

- **Designing experiments.** Guharajan *et al.* used RegulonDB to select binding sequences with strong evidence for 90 transcription factors, and built synthetic promoters with them to measure how each factor regulates transcription.
- **Interpreting new results.** Jago *et al.* used RegulonDB promoter and terminator annotations to classify intergenic antibiotic-resistance mutations by the regulatory feature they affect.

### References

- Guharajan S, Parisutham V, Brewster RC (2025). A systematic survey of TF function in *E. coli* suggests RNAP stabilization is a prevalent strategy for both repressors and activators. *Nucleic Acids Research*, 53(4). PMID: 39921566.
- Jago MJ, Soley JK, Denisov S, Walsh CJ, Gifford DR, Howden BP, Lagator M (2025). High-throughput method characterizes hundreds of previously unknown antibiotic resistance mutations. *Nature Communications*, 16:780. [doi:10.1038/s41467-025-56050-2](https://doi.org/10.1038/s41467-025-56050-2). PMID: 39824824.

## Story 2: Enabling Computational Method Development

### Context
New methods to infer gene regulatory networks must be compared against a reliable reference network.

### RegulonDB Contribution
RegulonDB is the source of the *E. coli* reference network ("ground truth") used to benchmark network inference methods.

### Example

- Stock *et al.* evaluated methods that use prior knowledge to infer gene regulatory networks; for *E. coli*, the benchmark ground truth (from the DREAM5 challenge) is curated from RegulonDB.

### Reference

- Stock M, Losert C, Zambon M, Popp N, Lubatti G, Hörmanseder E, Heinig M, Scialdone A (2025). Leveraging prior knowledge to infer gene regulatory networks from single-cell RNA-sequencing data. *Molecular Systems Biology*, 21(3):214–230. [doi:10.1038/s44320-025-00088-3](https://doi.org/10.1038/s44320-025-00088-3). PMID: 39939367.

## Story 3: Supporting Other Biodata Resources

### Context
Multi-species resources need curated regulatory knowledge to calibrate the regulatory links they predict.

### RegulonDB Contribution
RegulonDB is one of the sources of the regulatory gold standard used by FunCoup 6, a functional association network resource covering hundreds of species.

### Example

- FunCoup 6 added a new regulatory gold standard, built from RegulonDB together with TRRUST, RegNetwork, and Yeastract, to assign confidence to its directed regulatory links.
- More broadly, more than 70 databases and knowledge bases cite RegulonDB, including EcoCyc, PRODORIC, CoryneRegNet, RegPrecise, iModulonDB, and the *E. coli* genome-scale model iML1515 (see [Research Usage](research_usage.md)).

### Reference

- Buzzao D, Persson E, Guala D, Sonnhammer ELL (2025). FunCoup 6: advancing functional association networks across species with directed links and improved user experience. *Nucleic Acids Research*, 53(D1):D658–D671. [doi:10.1093/nar/gkae1021](https://doi.org/10.1093/nar/gkae1021). PMID: 39530220.

## Story 4: Improving Research Efficiency Through Reuse

### Context
Building a genome-wide regulatory network from the literature requires reading and interpreting thousands of articles. Few research groups can afford that effort for each new study.

### RegulonDB Contribution
RegulonDB offers the *E. coli* K-12 regulatory network already curated, with evidence and references for each interaction, so that other groups can start their analyses from it instead of rebuilding it. Several of the most cited studies in systems biology were built this way.

### Examples

- **New concepts.** Shen-Orr *et al.* built their *E. coli* transcriptional network on RegulonDB 3.2: 390 of its 577 interactions (about two thirds) came from RegulonDB, and the remaining 187 were added from the literature. With this network they identified **network motifs** such as the feed-forward loop, a concept that has since been applied across biology. The article has more than 2,300 citations.
- **Large-scale validation.** Faith *et al.* validated network inference algorithms applied to 445 *E. coli* microarrays against 3,216 experimentally determined regulatory interactions from RegulonDB.
- **Community benchmarks.** The DREAM5 network inference challenge (Marbach *et al.*) used RegulonDB to build the *E. coli* reference network, which is still used to benchmark new methods (see Story 2).

### Reach

In an analysis of the 2,455 documents citing RegulonDB (Scopus export of 31 March 2025), *network inference* (85 mentions), *systems biology* (95), and *machine learning* (51) were among the most frequent methodological terms, showing that much of the reuse consists of computational studies that take RegulonDB as their reference network.

### References

- Shen-Orr SS, Milo R, Mangan S, Alon U (2002). Network motifs in the transcriptional regulation network of *Escherichia coli*. *Nature Genetics*, 31(1):64–68. [doi:10.1038/ng881](https://doi.org/10.1038/ng881).
- Faith JJ, Hayete B, Thaden JT, *et al.* (2007). Large-scale mapping and validation of *Escherichia coli* transcriptional regulation from a compendium of expression profiles. *PLoS Biology*, 5(1):e8. [doi:10.1371/journal.pbio.0050008](https://doi.org/10.1371/journal.pbio.0050008).
- Marbach D, Costello JC, Küffner R, *et al.* (2012). Wisdom of crowds for robust gene network inference. *Nature Methods*, 9(8):796–804. [doi:10.1038/nmeth.2016](https://doi.org/10.1038/nmeth.2016).

## Story 5: Supporting Education and Skills Development

### Context
Training in regulatory genomics requires real, well-documented data that students can explore and analyze themselves.

### RegulonDB Contribution
RegulonDB provides curated binding sites and position-specific scoring matrices (PSSMs) for *E. coli* transcription factors, which are used in teaching to build and apply motif models.

### Example

- In the module **Bioinformática y Estadística II** of the undergraduate program in Genomic Sciences (Licenciatura en Ciencias Genómicas, LCG-UNAM), Dr. Jacques van Helden's practical "Scanning non-coding sequences with a TFBM" has students retrieve the binding sites and PSSM of a transcription factor (AraC) from RegulonDB and use them to scan regulatory sequences for new sites.

### Reference

- Course materials: [github.com/jvanheld/LCG_BEII](https://github.com/jvanheld/LCG_BEII) (practical `motif_search_RegulonDB`).

## Methodological Note

- This page reports public impact narratives based on citable references and reproducible resource usage patterns.
- Quantitative citation metrics are documented separately when available in dedicated usage reports.

## Related Pages

- [How to Cite RegulonDB](../00_about_policies/how_to_cite.md)
- [Version History](version_history.md)
- [Release Notes](release_notes.md)

## Last Review

- Last updated: 2026-11-18
- Responsible area: RegulonDB Documentation and Governance Team
