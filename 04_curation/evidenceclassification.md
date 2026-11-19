<img src="../assets/icons/curation.svg" alt="" width="48">

# Evidence Classification in RegulonDB

Scientific knowledge advances incrementally. At any point, we base broad conclusions on assertions of varying degrees of confidence. RegulonDB classifies evidence supporting particular assertions essentially based on the methods used to generate them. We do so to make explicit the complex mixture of more or less well supported specific claims that support broader conclusions (Weiss et al., 2013) In RegulonDB version 11.1 we made several changes to the collection of evidence types. We made changes to the evidence codes to make them more informative and more precise since we indicate the corresponding method. We increased the number of high throughput evidence types. Finally, we updated the collection of combinations of independent methods that increase the confidence levels. The details can be found in the sections on additive evidence below.

<br>

## Evidence supporting knowledge as ’Weak’, ’Strong ’ or ’Confirmed ’.

- **Weak evidence (W)**: Single evidence with more ambiguous conclusions, where alternative explanations, indirect effects, or potential false positives are prevalent, as well as computational predictions; for instance gel mobility shift assays with cell extracts or gene expression analysis.
- **Strong evidence (S)**: Single evidence with direct physical interaction or solid genetic evidence with a low probability for alternative explanations; for instance, footprinting with purified protein or site mutation.
- **Confirmed (C)**: is assigned, if objects are supported by at least two independent types of strong evidence with mutually excluding false positives. This approach is based essentially on the methods used to validate results and exclude alternative explanations in scientific research.


<br>

## Confidence Level Assignment

The confidence level is assigned in two stages:

- **In stage I**: we classify single evidence into weak or strong.  
- **In stage II**: we define combinations of independent evidence in a process termed “additive evidence” (previously described as Cross-Validation in (Weiss et al., 2013), that enable multiple weak evidence types to support an object with a strong (S) confidence level, as well as multiple strong types to support the higher “confirmed (C)” level of an object.

<br>

### Stage I. Classification of Individual Evidence Types

As mentioned before, in RegulonDB version 11.1 we made changes to the collection of evidence types; we changed the evidence codes so now they indicate the corresponding method (for instance Transcription initiation mapping is now encoded as primer extension assay for transcription start site determination evidence or S1 nuclease protection assay evidence for transcription start site determination evidence).
    
<br>

Single or individual Evidence is classified into weak(W) or strong(S) (see above), depending on the confidence level of the associated methodologies. 

<br>

#### 1. Promoters and transcription start sites (TSSs)

Promoters are defined in bacteria by the DNA region specifically bound by RNA polymerase to initiate transcription.
A TSS is the precise first nucleotide that is transcribed, different methods identify promoters or TSSs. They are jointly classified here.

<br>

| Confidence Level | Evidence Name                                           | EvidenceCode                        | Evidence Category          | Evidence Group | Object Type                                                                 |
|------------------|---------------------------------------------------------|-------------------------------------|----------------------------|:----------------:|-----------------------------------------------------------------------------|
| S                | RNA polymerase footprinting                             | EXP-IDA-RNA-POLYMERASE-FOOTPRINTING | Classical experiment       | 9              | Promoter                                                                    |
| S                | Transcription initiation mapping                        | EXP-IDA-TRANSCRIPTION-INIT-MAPPING  | Classical experiment       | 15             | Promoter                                                                    |
| S                | Site mutation                                           | EXP-IMP-SITE-MUTATION               | Classical binding          | 1              | Promoter;Regulatory Interactions;Transcription Factors                      |
| W                | Author hypothesis                                       | AS-HYPO                             | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Non-traceable author statement                          | AS-NAS                              | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Traceable author statement                              | AS-TAS                              | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Inferred by computational analysis                      | COMP                                | non-experimental           | 7              | Promoter;Regulatory Interactions;Transcription Factors                      |
| W                | Inferred computationally without human oversight        | COMP-AINF                           | non-experimental           | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Automated inference based on sequence pattern discovery | COMP-AINF-PATTERN-DISCOVERY         | non-experimental           | 7              | Promoter;Regulatory Interactions                                            |
| W                | Automated inference of promoter position                | COMP-AINF-POSITIONAL-IDENTIFICATION | non-experimental           | 7              | Promoter                                                                    |
| W                | Inferred by a human based on computational evidence     | COMP-HINF                           | non-experimental           | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Human inference of promoter position                    | COMP-HINF-POSITIONAL-IDENTIFICATION | non-experimental           | 7              | Promoter                                                                    |
| W                | Inferred from direct assay                              | EXP-IDA                             | Classical binding          |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | High-throughput transcription initiation mapping        | EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP | High-throughput protocol   | 10             | Promoter                                                                    |
| W                | in vitro transcription reconstitution assay evidence    | EXP-IDA-IN-VITRO-TRANSCRIPTION      | Classical expression       | 8              | Promoter                                                                    |
| W                | Inferred from expression pattern                        | EXP-IEP                             | Classical expression       | 8              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Northern blot for expression pattern analysis evidence  | EXP-IEP-NORTHERN                    | Classical expression       | 8              | Promoter;Regulatory Interactions                                            |
| W                | High-throughput RNA-seq evidence                        | EXP-IEP-RNA-SEQ                     | High-throughput expression | 8              | Promoter;Regulatory Interactions                                            |
| W                | Inferred from mutant phenotype                          | EXP-IMP                             | Classical binding          |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Inferred from physical interaction                      | EXP-IPI                             | Classical experiment       |                | Promoter;Regulatory Interactions;Transcription Factors                      |
| W                | Traceable author statement to experimental support      | EXP-TAS                             | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Inferred by curator                                     | IC                                  | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |


<br>
<br>

#### 2. Regulatory Interactions

A regulatory interaction is defined, depending on the type of evidence, as the transcription factor (TF)-regulated gene interaction (TF-gene), or more specifically as the TF-DNA binding site interaction.

| Confidence Level | Evidence Name                                                                                                        | Evidence Code                             | Evidence Category          | Evidence Group | Object Type                                                                     |
|------------------|----------------------------------------------------------------------------------------------------------------------|-------------------------------------------|----------------------------|:----------------:|---------------------------------------------------------------------------------|
| S                | Binding of purified proteins                                                                                         | EXP-IDA-BINDING-OF-PURIFIED-PROTEINS      | Classical binding          | 2              | Regulatory Interactions;Transcription Factors                                   |
| S                | Electrophoretic mobility shift assay with purified protein evidence                                                  | EXP-IDA-BINDING-OF-PURIFIED-PROTEINS-EMSA | Classical binding          | 2              | Regulatory Interactions;Transcription Factors                                   |
| S                | Site mutation                                                                                                        | EXP-IMP-SITE-MUTATION                     | Classical binding          | 1              | Promoter;Regulatory Interactions;Transcription Factors                          |
| W                | Author statement                                                                                                     | AS                                        | non-experimental           |                | Regulatory Interactions                                                         |
| W                | Author hypothesis                                                                                                    | AS-HYPO                                   | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                            |
| W                | Non-traceable author statement                                                                                       | AS-NAS                                    | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                            |
| W                | Traceable author statement                                                                                           | AS-TAS                                    | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                            |
| W                | Inferred by computational analysis                                                                                   | COMP                                      | non-experimental           | 7              | Promoter;Regulatory Interactions;Transcription Factors                          |
| W                | Inferred computationally without human oversight                                                                     | COMP-AINF                                 | non-experimental           | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors      |
| W                | Automated inference based on sequence pattern discovery                                                              | COMP-AINF-PATTERN-DISCOVERY               | non-experimental           | 7              | Promoter;Regulatory Interactions                                                |
| W                | Automated inference based on similarity to consensus sequences                                                       | COMP-AINF-SIMILAR-TO-CONSENSUS            | non-experimental           | 7              | Regulatory Interactions                                                         |
| W                | Inferred by a human based on computational evidence                                                                  | COMP-HINF                                 | non-experimental           | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors      |
| W                | Inferred from Sequence Alignment                                                                                     | COMP-HINF-ISA                             | non-experimental           |                | Regulatory Interactions;Transcription Factors                                   |
| W                | Manually curated inference based on sequence pattern discovery                                                       | COMP-HINF-PATTERN-DISCOVERY               | non-experimental           | 7              | Regulatory Interactions                                                         |
| W                | A person inferred or reviewed a computer inference of sequence function based on similarity to a consensus sequence. | COMP-HINF-SIMILAR-TO-CONSENSUS            | non-experimental           | 7              | Regulatory Interactions                                                         |
| W                | Inferred from Biological aspect from Ancestor                                                                        | COMP-IBA                                  | non-experimental           |                | Transcription Units;Regulatory Interactions                                     |
| W                | Inferred from experiment                                                                                             | EXP                                       |                            |                | Transcription Units;Regulatory Interactions;Transcription Factors               |
| W                | High-throughput ChIP-chip evidence                                                                                   | EXP-CHIP-CHIP                             | High-throughput binding    | 4              | Regulatory Interactions                                                         |
| W                | ChIP-chip evidence used in manual assertion                                                                          | EXP-CHIP-CHIP-MANUAL                      | High-throughput binding    | 4              | Regulatory Interactions                                                         |
| W                | High-throughput ChIP-exo evidence                                                                                    | EXP-CHIP-EXO                              | High-throughput binding    | 4              | Regulatory Interactions                                                         |
| W                | ChIP-exo evidence used in manual assertion                                                                           | EXP-CHIP-EXO-MANUAL                       | High-throughput binding    | 4              | Regulatory Interactions                                                         |
| W                | ChIP-PCR evidence                                                                                                    | EXP-CHIP-PCR                              | Classical experiment       | 4              | Regulatory Interactions                                                         |
| W                | ChIP-PCR evidence used in manual assertion                                                                           | EXP-CHIP-PCR-MANUAL                       | High-throughput binding    | 4              | Regulatory Interactions                                                         |
| W                | High-throughput ChIP-seq evidence                                                                                    | EXP-CHIP-SEQ                              | High-throughput binding    | 4              | Regulatory Interactions                                                         |
| W                | ChIP-seq evidence used in manual assertion                                                                           | EXP-CHIP-SEQ-MANUAL                       | High-throughput binding    | 4              | Regulatory Interactions                                                         |
| W                | High-throughput genomic SELEX-chip evidence                                                                          | EXP-GSELEX                                | High-throughput binding    | 5              | Regulatory Interactions                                                         |
| W                | Inferred from direct assay                                                                                           | EXP-IDA                                   | Classical binding          |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors      |
| W                | Binding of cellular extracts                                                                                         | EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS      | Classical binding          | 3              | Regulatory Interactions;Transcription Factors                                   |
| W                | Electrophoretic mobility shift assay with cellular extracts evidence                                                 | EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS-EMSA | Classical binding          | 3              | Regulatory Interactions                                                         |
| W                | Assay of protein purified to homogeneity                                                                             | EXP-IDA-PURIFIED-PROTEIN                  | Classical binding          |                | Regulatory Interactions;Transcription Factors                                   |
| W                | Inferred from expression pattern                                                                                     | EXP-IEP                                   | Classical expression       | 8              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors      |
| W                | Beta-galactosidase reporter gene assay evidence                                                                      | EXP-IEP-BETA-GAL                          | Classical expression       | 8              | Regulatory Interactions;Transcription Factors                                   |
| W                | Gene expression analysis                                                                                             | EXP-IEP-GENE-EXPRESSION-ANALYSIS          | Classical expression       | 8              | Regulatory Interactions;Transcription Factors                                   |
| W                | Green fluorescent protein reporter gene assay evidence                                                               | EXP-IEP-GFP                               | Classical expression       | 8              | Regulation-of-Transcription-Initiation,Proteins,Promoters,Transcription-Units   |
| W                | Luciferase reporter gene assay evidence                                                                              | EXP-IEP-LUCIFERASE                        | Classical expression       | 8              | Regulatory Interactions                                                         |
| W                | High-throughput expression microarray evidence                                                                       | EXP-IEP-MICROARRAY                        | High-throughput expression | 8              | Transcription Units;Regulatory Interactions                                     |
| W                | Northern blot for expression pattern analysis evidence                                                               | EXP-IEP-NORTHERN                          | Classical expression       | 8              | Promoter;Regulatory Interactions                                                |
| W                | Primer extension assay evidence for expression pattern analysis                                                      | EXP-IEP-PRIMER-EXTENSION-FOR-EXPRESSION   | Classical expression       | 8              | Regulatory Interactions                                                         |
| W                | Quantitative reverse transcription polymerase chain reaction evidence                                                | EXP-IEP-QRTPCR                            | Classical expression       | 8              | Regulatory Interactions                                                         |
| W                | High-throughput RNA-seq evidence                                                                                     | EXP-IEP-RNA-SEQ                           | High-throughput expression | 8              | Promoter;Regulatory Interactions                                                |
| W                | Reverse transcription polymerase chain reaction evidence                                                             | EXP-IEP-RTPCR                             | Classical expression       | 8              | Transcription Units;Regulatory Interactions                                     |
| W                | Inferred from genetic interaction                                                                                    | EXP-IGI                                   | Classical binding          |                | Regulatory Interactions;Transcription Factors                                   |
| W                | Inferred from mutant phenotype                                                                                       | EXP-IMP                                   | Classical binding          |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors      |
| W                | Reaction blocked in mutant                                                                                           | EXP-IMP-REACTION-BLOCKED                  | Classical binding          |                | Regulatory Interactions                                                         |
| W                | Inferred from physical interaction                                                                                   | EXP-IPI                                   | Classical experiment       |                | Promoter;Regulatory Interactions;Transcription Factors                          |
| W                | Nucleic acid binding evidence                                                                                        | EXP-NUC-ACID-BINDING                      | Classical experiment       |                | Regulatory Interactions                                                         |
| W                | Traceable author statement to experimental support                                                                   | EXP-TAS                                   | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                            |
| W                | High-throughput DNA affinity purification (DAP) sequencing                                                           | HTP-HDA-DAP-SEQ                           | High-throughput binding    | 6              | DNA-Binding-Sites,mRNA-Binding-Sites,Promoters,Proteins, Regulatory Interaction |
| W                | Inferred by curator                                                                                                  | IC                                        | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                            |


#### 3. Transcription Factor

Most dedicated TFs have usually two conformations, one with a non-covalent bound allosteric metabolite, or a covalent phosphorylation (holo conformation), and one as a free protein or multimer (the apo conformation). There are exceptions to this statement. We call functional conformation the one that is capable of binding to its specific binding sites and perform its activation or repression activity. For the sake of functional conformation evidence the experiments below have to be considered with and without effector. 

<br>

| Confidence Level | Evidence Name                                                                                                  | Evidence Code                             | Evidence Category    | Evidence Group | Object Type                                                                 |
|------------------|----------------------------------------------------------------------------------------------------------------|-------------------------------------------|----------------------|:----------------:|-----------------------------------------------------------------------------|
| S                | Binding of purified proteins                                                                                   | EXP-IDA-BINDING-OF-PURIFIED-PROTEINS      | Classical binding    | 2              | Regulatory Interactions;Transcription Factors                               |
| S                | Assay of protein purified to homogeneity from a heterologous host                                              | EXP-IDA-PURIFIED-PROTEIN-HH               | Classical experiment |                | Transcription Factors                                                       |
| S                | Inferred by functional complementation                                                                         | EXP-IGI-FUNC-COMPLEMENTATION              | Classical experiment |                | Transcription Factors                                                       |
| S                | Site mutation                                                                                                  | EXP-IMP-SITE-MUTATION                     | Classical binding    | 1              | Promoter;Regulatory Interactions;Transcription Factors                      |
| S                | Assay of protein purified to homogeneity from its native host                                                  | IDA-PURIFIED-PROTEIN-NH                   | Classical experiment |                | Transcription Factors                                                       |
| W                | Inferred by computational analysis                                                                             | COMP                                      | non-experimental     | 7              | Promoter;Regulatory Interactions;Transcription Factors                      |
| W                | Inferred computationally without human oversight                                                               | COMP-AINF                                 | non-experimental     | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Automated inference of function from sequence                                                                  | COMP-AINF-FN-FROM-SEQ                     | non-experimental     |                | Transcription Factors                                                       |
| W                | Automated inference of function by sequence orthology                                                          | COMP-AINF-SEQ-ORTHOLOGY                   | non-experimental     |                | Transcription Factors                                                       |
| W                | Inferred by a human based on computational evidence                                                            | COMP-HINF                                 | non-experimental     | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Human inference of function from sequence                                                                      | COMP-HINF-FN-FROM-SEQ                     | non-experimental     |                | Transcription Factors                                                       |
| W                | Inferred from Sequence Alignment                                                                               | COMP-HINF-ISA                             | non-experimental     |                | Regulatory Interactions;Transcription Factors                               |
| W                | Inferred from Sequence Model                                                                                   | COMP-HINF-ISM                             | non-experimental     |                | Transcription Factors                                                       |
| W                | Human inference of function based on ortholog with experimental function in closely related strain or species. | COMP-HINF-ORTHOLOGY-EXP                   | non-experimental     |                | Transcription Factors                                                       |
| W                | Inferred from experiment                                                                                       | EXP                                       |                      |                | Transcription Units;Regulatory Interactions;Transcription Factors           |
| W                | Inferred from direct assay                                                                                     | EXP-IDA                                   | Classical binding    |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Binding of cellular extracts                                                                                   | EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS      | Classical binding    | 3              | Regulatory Interactions;Transcription Factors                               |
| W                | Assay of partially-purified protein                                                                            | EXP-IDA-PART-PURIFIED-PROTEIN             | Classical experiment |                | Transcription Factors                                                       |
| W                | Assay of protein partially-purified from a heterologous host                                                   | EXP-IDA-PART-PURIFIED-PROTEIN-HH          | Classical experiment |                | Transcription Factors                                                       |
| W                | Assay of protein partially-purified from its native host                                                       | EXP-IDA-PART-PURIFIED-PROTEIN-NH          | Classical experiment |                | Transcription Factors                                                       |
| W                | Assay of protein purified to homogeneity                                                                       | EXP-IDA-PURIFIED-PROTEIN                  | Classical binding    |                | Regulatory Interactions;Transcription Factors                               |
| W                | Assay of unpurified protein                                                                                    | EXP-IDA-UNPURIFIED-PROTEIN                | Classical experiment |                | Transcription Factors                                                       |
| W                | Assay of unpurified protein expressed in its native host                                                       | EXP-IDA-UNPURIFIED-PROTEIN-NH             | Classical experiment |                | Transcription Factors                                                       |
| W                | Inferred from expression pattern                                                                               | EXP-IEP                                   | Classical expression | 8              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Beta-galactosidase reporter gene assay evidence                                                                | EXP-IEP-BETA-GAL                          | Classical expression | 8              | Regulatory Interactions;Transcription Factors                               |
| W                | Gene expression analysis                                                                                       | EXP-IEP-GENE-EXPRESSION-ANALYSIS          | Classical expression | 8              | Regulatory Interactions;Transcription Factors                               |
| W                | Inferred from genetic interaction                                                                              | EXP-IGI                                   | Classical binding    |                | Regulatory Interactions;Transcription Factors                               |
| W                | Inferred from mutant phenotype                                                                                 | EXP-IMP                                   | Classical binding    |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Inferred from physical interaction                                                                             | EXP-IPI                                   | Classical experiment |                | Promoter;Regulatory Interactions;Transcription Factors                      |
|                  | Electrophoretic mobility shift assay with purified protein evidence                                            | EXP-IDA-BINDING-OF-PURIFIED-PROTEINS-EMSA | Classical binding    | 2              | Regulatory Interactions;Transcription Factors                               |

<br>
<br>


#### 4. Transcription Units


| Confidence Level | Evidence Name                                                            | Evidence Code                                 | Evidence Category          | Evidence Group | Object Type                                                                 |
|------------------|--------------------------------------------------------------------------|-----------------------------------------------|----------------------------|:----------------:|-----------------------------------------------------------------------------|
| S                | Length of transcript experimentally determined                           | EXP-IDA-TRANSCRIPT-LEN-DETERMINATION          | Classical experiment       | 11             | Transcription Units                                                         |
| S                | Polar mutation                                                           | EXP-IMP-POLAR-MUTATION                        | Classical experiment       | 12             | Transcription Units                                                         |
| W                | Author hypothesis                                                        | AS-HYPO                                       | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Non-traceable author statement                                           | AS-NAS                                        | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Traceable author statement                                               | AS-TAS                                        | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Inferred computationally without human oversight                         | COMP-AINF                                     | non-experimental           | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Automated inference that a single-gene directon is a transcription unit  | COMP-AINF-SINGLE-DIRECTON                     | non-experimental           | 13             | Transcription Units                                                         |
| W                | Inferred by a human based on computational evidence                      | COMP-HINF                                     | non-experimental           | 7              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Inferred from Biological aspect from Ancestor                            | COMP-IBA                                      | non-experimental           |                | Transcription Units;Regulatory Interactions                                 |
| W                | Inferred from experiment                                                 | EXP                                           |                            |                | Transcription Units;Regulatory Interactions;Transcription Factors           |
| W                | Inferred from direct assay                                               | EXP-IDA                                       | Classical binding          |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Boundaries of transcription experimentally identified                    | EXP-IDA-BOUNDARIES-DEFINED                    | Classical experiment       | 14             | Transcription Units                                                         |
| W                | Inferred from expression pattern                                         | EXP-IEP                                       | Classical expression       | 8              | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Inferred through co-regulation                                           | EXP-IEP-COREGULATION                          | Classical experiment       |                | Transcription Units                                                         |
| W                | High-throughput expression microarray evidence                           | EXP-IEP-MICROARRAY                            | High-throughput expression | 8              | Transcription Units;Regulatory Interactions                                 |
| W                | Reverse transcription polymerase chain reaction evidence                 | EXP-IEP-RTPCR                                 | Classical expression       | 8              | Transcription Units;Regulatory Interactions                                 |
| W                | Inferred from mutant phenotype                                           | EXP-IMP                                       | Classical binding          |                | Promoter;Transcription Units;Regulatory Interactions;Transcription Factors  |
| W                | Traceable author statement to experimental support                       | EXP-TAS                                       | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Inferred from high throughput expression pattern                         | HTP-HEP                                       | High-throughput protocol   |                | Transcription Units                                                         |
| W                | Inferred by curator                                                      | IC                                            | non-experimental           |                | Promoter;Transcription Units;Regulatory Interactions                        |
| W                | Products of adjacent genes in the same biological process                | IC-ADJ-GENES-SAME-BIO-PROCESS                 | non-experimental           |                | Transcription Units                                                         |
| W                | No biological data available                                             | ND                                            | non-experimental           |                | Transcription Units                                                         |
|                  | Northern blot for transcription unit length determination evidence       | EXP-IDA-TRANSCRIPT-LEN-DETERMINATION-NORTHERN |                            | 11             | Transcription Units                         |


<br>
<br>

### Stage II. Assignment of confidence level based on additive evidence types

Following the same logic described in ([Weiss et al., 2013](https://pubmed.ncbi.nlm.nih.gov/23327937/)) we integrate multiple evidence by combining independent types of evidence, with the intention to confirm individual objects and mutually exclude false positives. It follows the same principles of science as applied by wet-lab scientists, where data are confirmed by repetitions on the one hand, and by additional experimental strategies to exclude alternative explanations on the other. This approach allows us to combine classic methods from molecular biology and genomic high throughput (HT) methods.
<br>

Additive evidence (called "cross-validation" in previous releases of RegulonDB) requires that the combined methods are independent, that is, do not share major sources of false positives or common raw materials. In this version the evidence codes were assigned to an evidence group, different evidence groups correspond to independent methods. Evidence codes from the same evidence group cannot be combined to upgrade the object confidence level. Some evidence groups are shared among diverse object types, i.e. EXP-IMP-SITE-MUTATION is associated with regulatory interactions and also with promoters, while other classes are exclusive of an object type.
<br>

Objects that are supported by multiple types of independent weak (W) evidence are classified as strong evidence (S). A third confidence score "confirmed"(C) is assigned to objects that are supported by two types of independent strong evidence. In the table below are indicated the combinations of evidence groups that result in upgrade to strong or confirmed confidence level of an object. i.e. the combination (8/10/7) results in a confirmed confidence level; it happens when the object has at least one evidence code from the evidence groups 8, 10 and 7.

The downloadable datasets contain all the individual evidence types so users can either construct their own combinations or use the three confidence levels (W,S,C). 

<br>

#### 1. Promoters and transcription start sites (TSSs)

| Additive Evidence Rule  | Evidences|
|:--      |:--       |
| **Confirmed Evidence** |    |
| Additive Evidence (1/9) |	1: (EXP-IMP-SITE-MUTATION) <br> 9: (EXP-IDA-RNA-POLYMERASE-FOOTPRINTING) |
| Additive Evidence (1/7/10) |	1: (EXP-IMP-SITE-MUTATION) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-AINF-POSITIONAL-IDENTIFICATION, COMP-HINF-POSITIONAL-IDENTIFICATION, COMP-HINF, COMP, COMP-AINF) <br> 10: (EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP) |
| Additive Evidence (1/15) |	1: (EXP-IMP-SITE-MUTATION) <br> 15: (EEV-EXP-IDA-TRANSCRIPTION-INIT-MAPPING,EXP-IDA-TRANSCRIPTION-INIT-MAPPING-PRIMER-EXTENSION-TSS, EXP-IDA-TRANSCRIPTION-INIT-MAPPING-S1) |
| Additive Evidence (7/10/15) | 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-AINF-POSITIONAL-IDENTIFICATION, COMP-HINF-POSITIONAL-IDENTIFICATION, COMP-HINF, COMP, COMP-AINF) <br> 10: (EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP) <br> 15: (EEV-EXP-IDA-TRANSCRIPTION-INIT-MAPPING,EXP-IDA-TRANSCRIPTION-INIT-MAPPING-PRIMER-EXTENSION-TSS, EXP-IDA-TRANSCRIPTION-INIT-MAPPING-S1) |
| Additive Evidence (9/15) |	9: (EXP-IDA-RNA-POLYMERASE-FOOTPRINTING) <br> 15: (EEV-EXP-IDA-TRANSCRIPTION-INIT-MAPPING,EXP-IDA-TRANSCRIPTION-INIT-MAPPING-PRIMER-EXTENSION-TSS, EXP-IDA-TRANSCRIPTION-INIT-MAPPING-S1) |
| Additive Evidence (7/9/10) | 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-AINF-POSITIONAL-IDENTIFICATION, COMP-HINF-POSITIONAL-IDENTIFICATION, COMP-HINF, COMP, COMP-AINF) <br>  9: (EXP-IDA-RNA-POLYMERASE-FOOTPRINTING) <br> 10: (EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP)  |
| **Strong Evidence** | |
| Additive Evidence (7/10) | 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-AINF-POSITIONAL-IDENTIFICATION, COMP-HINF-POSITIONAL-IDENTIFICATION, COMP-HINF, COMP, COMP-AINF)  <br>  10: (EXP-IDA-HPT-TRANSCR-INIT-M-RACE-MAP)|

<br>

#### 2. Regulatory interactions

| Additive Evidence Rule  | Evidences|
|:--      |:--       |
| **Confirmed Evidence** 	| |
| Additive Evidence (1/2) | 1: (EXP-IMP-SITE-MUTATION) <br> 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) |
| Additive Evidence(1/3/4/8) | 1: (EXP-IMP-SITE-MUTATION) <br> 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
|Additive Evidence (1/3/5/8) | 1: (EXP-IMP-SITE-MUTATION) <br>  3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 5: (EXP-GSELEX) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence(1/3/6/8)| 1: (EXP-IMP-SITE-MUTATION) <br> 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br>  6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)|
| Additive Evidence(1/3/7/8) | 1: (EXP-IMP-SITE-MUTATION) <br> 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence (1/4/5/8) | 1: (EXP-IMP-SITE-MUTATION) <br>  4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 5: (EXP-GSELEX) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY, EXP-IEP-RTPCR)  |
| Additive Evidence (1/4/6/8)| 1: (EXP-IMP-SITE-MUTATION) <br>  4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 6: (HTP-HDA-DAP-SEQ) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY, EXP-IEP-RTPCR) |
| Additive Evidence (1/4/7/8) | 1: (EXP-IMP-SITE-MUTATION)  <br>  4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br>  7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)|
| Additive Evidence (1/5/6/8)| 1: (EXP-IMP-SITE-MUTATION) <br> 5: (EXP-GSELEX) <br>  6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)|
| Additive Evidence (1/5/7/8)  | 1: (EXP-IMP-SITE-MUTATION) <br>  5: (EXP-GSELEX) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence (1/6/7/8)  | 1: (EXP-IMP-SITE-MUTATION) <br>  6: (HTP-HDA-DAP-SEQ) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence (2/3/4/8) | 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br>  3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (2/3/5/8) |2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br>  3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 5: (EXP-GSELEX) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)   |
| Additive Evidence (2/3/6/8) |2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br>  3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)   |
| Additive Evidence (2/3/7/8) |2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br>  3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence (2/4/5/8) | 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 5: (EXP-GSELEX) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (2/4/6/8) | 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (2/4/7/8) | 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  | 
| Additive Evidence (2/5/6/8) | 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br> 5: (EXP-GSELEX) <br> 6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (2/5/7/8) | 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br> 5: (EXP-GSELEX) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (2/6/7/8) | 2: (EXP-IDA-BINDING-OF-PURIFIED-PROTEINS) <br> 6: (HTP-HDA-DAP-SEQ) <br>7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (3/4/5/6/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 5: (EXP-GSELEX) <br> 6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (3/4/5/7/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 5: (EXP-GSELEX) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (3/4/6/7/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 6: (HTP-HDA-DAP-SEQ) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (3/5/6/7/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br>  5: (EXP-GSELEX) <br> 6: (HTP-HDA-DAP-SEQ) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence (4/5/6/7/8) | 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br>  5: (EXP-GSELEX) <br> 6: (HTP-HDA-DAP-SEQ) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| **Strong Evidence** | |
| Additive Evidence (3/4/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence(3/5/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 5: (EXP-GSELEX) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence(3/6/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br> 6: (HTP-HDA-DAP-SEQ) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence(3/7/8) | 3: (EXP-IDA-BINDING-OF-CELLULAR-EXTRACTS) <br>  7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence(4/5/8) | 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 5: (EXP-GSELEX) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence(4/6/8) | 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence(4/7/8) | 4: (EXP-CHIP-PCR-MANUAL, EXP-CHIP-CHIP-MANUAL, EXP-CHIP-EXO-MANUAL, EXP-CHIP-SEQ-MANUAL, EXP-CHIP-CHIP, EXP-CHIP-EXO, EXP-CHIP-SEQ) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence (5/6/8) | 5: (EXP-GSELEX) <br> 6: (HTP-HDA-DAP-SEQ) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |
| Additive Evidence(5/7/8) | 5: (EXP-GSELEX) <br>  7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br> 8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY) |
| Additive Evidence (6/7/8) | 6: (HTP-HDA-DAP-SEQ) <br> 7: (COMP-HINF-SIMILAR-TO-CONSENSUS, COMP-AINF-PATTERN-DISCOVERY, COMP-AINF-SIMILAR-TO-CONSENSUS, COMP-HINF, COMP, COMP-AINF, COMP-HINF-PATTERN-DISCOVERY) <br>  8: (EXP-IEP-GENE-EXPRESSION-ANALYSIS, EXP-IEP, EXP-IEP-RNA-SEQ, EXP-IEP-MICROARRAY)  |

<br>

#### 3. Transcription Units

| Additive Evidence Rule  | Evidences|
|:--      |:--       |
| **Confirmed Evidence** 	| |
| Additive Evidence (11/12)| 11: (EV-EXP-IDA-TRANSCRIPT-LEN-DETERMINATION, EXP-IDA-TRANSCRIPT-LEN-DETERMINATION-NORTHERN) <br> 12: (EV-EXP-IMP-POLAR-MUTATION) |
| **Strong Evidence** 	| |
|Additive Evidence (13/14)| 13: (EV-COMP-AINF-SINGLE-DIRECTON) <br> 14: (EV-EXP-IDA-BOUNDARIES-DEFINED)|

## References

- Weiss V, Medina-Rivera A, Huerta AM, *et al.* (2013). Evidence classification of high-throughput protocols and confidence integration in RegulonDB. *Database (Oxford)* 2013:bas059. [doi:10.1093/database/bas059](https://doi.org/10.1093/database/bas059)

## Related Content

- [RegulonDB Glossary: Evidence and Confidence Level](glossary/glossary.md#evidence-and-confidence-level)
- [Collection: Evidences](../07_technical_reference/core_collections/collection_evidences.md)
- [Collection: Additive Evidences](../07_technical_reference/core_collections/collection_additive_evidences.md)
- [Gold Standard Guide](../02_data_access/gold_standard_guide_en.md)

## Last Review

- Last updated: 2026-11-19
- Maintained by: RegulonDB Team
