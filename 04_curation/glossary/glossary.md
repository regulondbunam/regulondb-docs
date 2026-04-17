
# RegulonDB Glossary


## Introduction to Gene Expression

Gene expression in bacteria is controlled through a wide variety of regulatory mechanisms that allow cells to respond rapidly to environmental and physiological signals. Classical studies of bacterial gene regulation established that transcription initiation is frequently controlled by transcription factors (TFs) that bind specific DNA sequences near promoters and modulate the activity of RNA polymerase. These regulatory interactions form the basis of transcriptional regulatory networks that coordinate the expression of multiple genes.
Over the past decades, extensive experimental and computational efforts have produced large collections of regulatory knowledge describing TFs, promoters, transcription units, and regulatory interactions in bacterial genomes. 

Bacterial gene expression is regulated not only at the level of transcription but also at later stages of gene expression. In particular, regulatory RNAs have emerged as important regulators of gene expression, frequently acting at the level of translation initiation through interactions with messenger RNAs (mRNAs). Trans-acting small RNAs often regulate gene expression by base pairing with target mRNAs near the ribosome binding site, thereby altering ribosome access and translation efficiency. In addition, cis-acting RNA elements such as riboswitches can alter transcription termination or translation initiation through ligand-induced structural rearrangements of the RNA molecule. Regulation also occur by direct interaction of regulatory metabolites interacting with RNA polymerase.


Databases such as RegulonDB have played a central role in organizing this knowledge and providing curated representations of transcriptional regulatory networks.




# Gene (Gen)

## 2. Definición simple

Un **gen** es una región continua de ADN que contiene la información necesaria para producir al menos un producto funcional, como un RNA o una proteína.

## 3. Definición extendida

En RegulonDB, un **gen** es una región de ADN mayor a cero nucleótidos que codifica uno o más productos funcionales. Estos productos pueden incluir RNAs funcionales (tRNA, rRNA, sRNA, etc.) o proteínas. La definición contempla casos complejos como:

* inicio de traducción alternativo,
* marcos de lectura alternativos,
* cambios de marco (frameshifting),
* procesamiento de RNA.

RegulonDB también registra genes sin productos funcionales actuales (pseudogenes o phantom genes) para preservar coherencia histórica.

## 4. Acrónimos y sinónimos relevantes

* gene
* genetic locus (histórico, no recomendado)
* ORF (relacionado, pero no equivalente)

## 5. Propiedades mínimas del objeto

| Propiedad      | Descripción                            | Requerida | Ejemplo      |
| -------------- | -------------------------------------- | --------- | ------------ |
| position left  | posición absoluta inicial en el genoma | sí        | 190          |
| position right | posición absoluta final en el genoma   | sí        | 255          |
| strand         | hebra del ADN donde se ubica el gen    | sí        | forward      |
| sequence       | secuencia del gen                      | sí        | ATGAAACGC... |
| synonyms       | otros nombres asociados                | no        | EG11277      |

## 6. Representación gráfica del objeto

En RegulonDB, un gen se visualiza como un rectángulo orientado según la hebra (forward/reverse). La dirección indica el sentido de transcripción. Los genes suelen mostrarse contiguos dentro de operones o aislados.

![](./images/gene.png).  
Figure. Graphical representation of DNA region with a gene. RegulonDB´s Drawing Traces Tool [image].


## 7. Comments (Notas importantes)

* Un gen es una unidad informacional del genoma.
* No todos los genes pertenecen a operones.
* La regulación no ocurre a nivel de gen, sino a nivel de promotores, TUs y operones.
* Genes con múltiples productos representan adecuadamente fenómenos como isoformas proteicas o RNAs procesados.

## 8. Ejemplos

**Ejemplo simple:** un gen proteico típico con un único producto.

**Ejemplo complejo:** *dnaX*, que produce las proteínas tau y gamma mediante frameshifting.

## 9. Conexiones conceptuales

* **Gene → Product:** un gen genera uno o más productos.
* **Gene → Transcription Unit:** el gen puede estar contenido en una o varias TUs.
* **Gene ≠ CDS:** un gen puede tener varias CDS asociadas si produce isoformas.
* **Gene ≠ Regulador:** un gen puede codificar un regulador, pero el concepto no es equivalente.

## 10. Errores comunes o confusiones del usuario

* Confundir gen con CDS.
* Asumir que todos los genes están regulados por un único promotor.
* Pensar que el gen es la unidad de regulación. No lo es.

## 11. Referencias

* Mejía-Almonte et al., 2020. Redefining fundamental concepts of transcription initiation in bacteria.


## 12. Useful links

- Gene product (Wikipedia): https://en.wikipedia.org/wiki/Gene_product
- Biology Online – Gene Product: https://www.biologyonline.com/dictionary/gene-product
- UniProt (proteins): https://www.uniprot.org
- Rfam (functional RNAs): https://rfam.org

## 13. Historial del concepto

La definición se ha mantenido estable, pero RegulonDB ha extendido su representación para capturar:

* genes con múltiples productos,
* pseudogenes,
* phantom genes.


---

# Product (Producto Génico)

## 2. Definición simple

Un **producto génico** es la molécula funcional derivada de un gen: un RNA funcional o una proteína.

## 3. Definición extendida

En RegulonDB, un **product** es la molécula final funcional generada durante la expresión de un gen. Puede ser:

* Un **RNA funcional** (tRNA, rRNA, sRNA, tmRNA, etc.)
* Una **proteína**, incluyendo isoformas originadas por:

  * codones de inicio alternativos,
  * marcos alternativos de lectura,
  * procesamiento postraduccional.

**Importante:** El **mRNA no se considera un producto funcional**, sino un intermediario. Solo los RNAs con función propia se consideran productos.

## 4. Acrónimos y sinónimos relevantes

* gene product
* protein product
* RNA product

## 5. Propiedades mínimas del objeto

| Propiedad         | Descripción                            | Requerida | Ejemplo           |
| ----------------- | -------------------------------------- | --------- | ----------------- |
| product name      | nombre del producto                    | no        | ApaG              |
| gene id           | identificador del gen que lo produce   | sí        | RDBECOLIGNC00043  |
| sequence          | secuencia proteica o RNA funcional     | sí        | MKRISTTIT...      |
| product type      | tipo de producto (protein, sRNA, tRNA) | no        | small RNA         |
| molecular weight  | peso molecular estimado                | no        | 13.867 kDa        |
| cellular location | localización celular                   | no        | periplasmic space |

## 6. Representación gráfica del objeto

En RegulonDB, los productos no se visualizan directamente en el mapa genómico, pero aparecen como:

* entidades en paneles de información del gen,
* participantes en reacciones,
* componentes de complejos,
* elementos dentro de los GENSOR Units.


![](./images/product.png).   
Figure. Gene Definition. Biology Online of Digital Ventures Corporation URL: https://www.biologyonline.com/dictionary/gene.

## 7. Comments (Notas importantes)

* Un mismo gen puede producir múltiples productos.
* La versatilidad de un producto depende de su secuencia y modificaciones.
* Algunos productos funcionan como **reguladores** (TFs, sRNAs), pero no todos.
* Los productos proteicos pueden incluir isoformas no triviales.

## 8. Ejemplos

**Ejemplo simple:** Producto proteico único derivado de un gen típico.

**Ejemplo complejo:** *dnaX* → tau y gamma mediante frameshift.

## 9. Conexiones conceptuales

* **Product → Function:** cada producto tiene funciones moleculares.
* **Product → Complex:** los productos son componentes de complejos.
* **Product → GENSOR Unit:** los productos participan en reacciones y respuestas.
* **Product ≠ mRNA:** el mRNA no es producto final.

## 10. Errores comunes

* Creer que mRNA es un producto funcional.
* Pensar que un gen siempre produce un solo producto.
* Confundir producto con gen, CDS o regulador.

## 11. Referencias

* Gene product. Wikipedia.
* Gama-Castro et al., RegulonDB.

## 12. Useful links

- Gene product (Wikipedia): https://en.wikipedia.org/wiki/Gene_product
- Biology Online – Gene Product: https://www.biologyonline.com/dictionary/gene-product
- UniProt (proteins): https://www.uniprot.org
- Rfam (functional RNAs): https://rfam.org


## 13. Historial del concepto

El concepto de producto se amplió para capturar isoformas proteicas y RNAs funcionales adicionales.

La definición se ha mantenido estable, pero RegulonDB ha extendido su representación para capturar:

* genes con múltiples productos,
* pseudogenes,
* phantom genes.


---


# Promoter (Promotor)

## 2. Definición simple
Un **promotor** es una región específica del ADN donde la ARN polimerasa holoenzima (Eσ) se une para iniciar la transcripción. Define el punto donde comienza un RNA (TSS) y determina qué genes o unidades transcripcionales pueden expresarse.

## 3. Definición extendida
En RegulonDB, un **promoter** es una región de ADN reconocida por una holoenzima compuesta por la ARN polimerasa y un factor sigma específico. Su función es guiar a la enzima hacia el sitio donde se inicia la transcripción, definido por el nucleótido +1 o **Transcription Start Site (TSS)**.

Los promotores presentan elementos característicos, tales como:
- **Cajas de reconocimiento** (-10 y -35 para σ70, -12/-24 para σ54),
- **Elementos extendidos**, como la región extendida -10,
- **Elementos UP**, que potencian la afinidad con la ARN polimerasa,
- **Regiones discriminadoras**, asociadas a respuestas específicas como la limitación de aminoácidos.

Un mismo TSS puede estar asociado a **diferentes promotores**, cuando distintos sigma factores reconocen elementos superpuestos (ej. glmY). A la inversa, un promotor puede presentar múltiples TSS dentro de una ventana de ±5 nucleótidos debido a la variabilidad natural en la apertura del complejo de iniciación.

En RegulonDB, el nombre del promotor deriva del **primer gen transcrito**, seguido de una “p”.

## 4. Acrónimos y sinónimos relevantes
- promoter
- promoter region
- transcription initiation site (a veces usado de forma imprecisa)
- sigma factor recognition site

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| promoter name | Nombre asignado por RegulonDB | sí | caiFp |
| sigma factor | Factor sigma que reconoce el promotor | sí | sigma70 |
| TSS | Posición genómica del sitio de inicio de transcripción (+1) | sí | 34218 |
| sequence | Secuencia del promotor, con el +1 en mayúsculas | sí | gatgacata...Atccacaa |
| strand | Hebra del ADN donde se localiza el promotor | sí | forward |
| boxes | Elementos de reconocimiento sigma (-10, -35, etc.) | no | ctcaca / tactat |

## 6. Representación gráfica del objeto
En RegulonDB, un promotor se muestra como un pequeño símbolo triangular o una marca direccional indicando el sitio de inicio de transcripción. Se representa inmediatamente antes de las unidades transcripcionales y genes regulados.

Los sitios -10, -35 y otros elementos pueden visualizarse en paneles detallados. Los promotores superpuestos se representan como múltiples símbolos en la misma posición genómica con diferentes identificadores de sigma factor.

![](./images/promoter.png).  
Figure: Graphical representation of a promoter. RegulonDB´s Drawing Traces Tool.

## 7. Comments (Notas importantes)
- Un promotor regula **una unidad transcripcional (TU)**, no necesariamente un solo gen.
- Diferentes promotores pueden compartir el mismo TSS.
- Un gen puede tener múltiples promotores, lo que permite expresión diferencial.
- Los promotores pueden estar superpuestos o incluso ubicarse dentro de operones complejos.
- No todos los promotores presentan motivo -10/-35 canónicos.
- Factores sigma alternativos definen clases funcionales de promotores.

## 8. Ejemplos
**Ejemplo simple (σ70):**  
Promotor bien definido con cajas -10 y -35 conservadas y un único TSS predominante.

**Ejemplo complejo (promotores superpuestos):**  
El gen glmY presenta promotores reconocidos por σ70 y σ54 que comparten el mismo TSS, definiéndose como promotores distintos.

## 9. Conexiones conceptuales
- **Promoter → TU:** determina el inicio de la unidad transcripcional.
- **Promoter ↔ Sigma factor:** cada promotor está asociado a un sigma específico.
- **Promoter ↔ Regulatory Sites (TFRS):** los promotores pueden ser blanco de activadores o represores.
- **Promoter → Operon:** un operón puede tener varios promotores que generan transcritos alternativos.
- **Promoter ≠ TSS:** el TSS es parte del promotor, pero no es el promotor.

## 10. Errores comunes
- Confundir el promotor con la región upstream del gen.
- Asumir que un promotor regula un único gen.
- Pensar que todos los promotores tienen cajas -10/-35 perfectamente conservadas.
- Igualar TSS a promotor.

## 11. Referencias
- Mejía-Almonte C, et al. 2020. *Redefining fundamental concepts of transcription initiation in bacteria*. Nature Reviews Genetics. https://doi.org/10.1038/s41576-020-0254-8

## 12. Useful links
- Wikipedia – Promoter: https://en.wikipedia.org/wiki/Promoter_(genetics)
- Biology Online – Promoter: https://www.biologyonline.com/dictionary/promoter
- RegulonDB – Ejemplos de promotores: https://regulondb.ccg.unam.mx

## 13. Historial del concepto
- Originalmente se definía solo por cajas -10/-35.
- A partir de 2020, incorporó nuevas regiones funcionales y la posibilidad de múltiples TSS.
- Se oficializó la distinción entre promotores que comparten TSS pero reconocen distintos sigma factores.


---

# Terminator (Terminador)

## 2. Definición simple
Un **terminador** es una región del ADN donde la ARN polimerasa detiene la transcripción y libera el RNA recién sintetizado. Marca el final de una unidad transcripcional.

## 3. Definición extendida
En RegulonDB, un **terminator** es una región genómica que provoca la terminación de la transcripción por uno de dos mecanismos principales:

- **Terminadores independientes de Rho (rho-independent o intrínsecos)**: contienen una secuencia invertida rica en GC que forma una horquilla en el RNA, seguida de una cola de U en la molécula de RNA, lo que desestabiliza el complejo de transcripción.
- **Terminadores dependientes de Rho (rho-dependent)**: requieren la acción de la proteína Rho, una helicasa que persigue al RNA polimerasa y promueve la disociación del complejo.

Los terminadores delimitan el final de una **unidad transcripcional (TU)**, pero no necesariamente del último gen transcrito. Un terminador puede estar asociado a más de una TU, especialmente en operones complejos.

## 4. Acrónimos y sinónimos relevantes
- terminator
- TTS (Transcription Termination Site)
- intrinsic terminator (rho-independent)
- rho-dependent terminator

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| left position | inicio de la región del terminador | sí | 274 |
| right position | fin de la región del terminador | sí | 310 |
| strand | hebra donde ocurre la terminación | sí | forward |
| sequence | secuencia del terminador | sí | ggaaacacagAAAAAAG..GGCTTTTTTTTTcgaccaaagg |
| type | tipo de terminación | sí | rho-independent |
| transcriptionUnit(s) | TU(s) afectadas | no | thrLABC |

## 6. Representación gráfica del objeto
En RegulonDB, los terminadores se muestran como un símbolo de "T" invertida o figura similar que indica el final de una TU. Pueden aparecer:
- como límites finales de un operón,
- como terminadores internos en operones complejos,
- asociados a múltiples unidades transcripcionales.

![](./images/terminator.png)


## 7. Comments (Notas importantes)
- Un terminador no está asociado a un solo gen, sino a **una o más TUs**.
- Existen terminadores internos que generan transcritos alternativos en operones complejos.
- La eficiencia de terminación puede variar; algunos terminadores permiten **readthrough**.
- Los terminadores intrínsecos son los más fácilmente predecibles computacionalmente.
- Los terminadores dependientes de Rho requieren evidencia experimental o inferencias basadas en características de secuencia.
- Los atenuadores son un caso especial de terminadores regulados por traducción de un péptido líder.

## 8. Ejemplos
**Ejemplo simple:** 
Un terminador rho-independent con horquilla GC y cola de U.

**Ejemplo complejo:** 
El terminador asociado al operón *thrLABC*, que funciona como límite para múltiples TUs.

## 9. Conexiones conceptuales
- **Promoter → Terminator:** ambos delimitan una TU.
- **Terminator → TU:** determina dónde termina una unidad transcripcional.
- **Terminator → Operon:** un operón puede tener múltiples terminadores internos.
- **Terminator vs Attenuator:** el atenuador es un terminador regulado cuyo funcionamiento depende de la traducción del péptido líder.
- **Terminator ≠ sitio regulatorio:** no media unión de factores, aunque su estructura influye en la regulación.

## 10. Errores comunes
- Creer que el terminador corresponde a un gen específico.
- Pensar que el terminador está siempre al final de un operón.
- Asumir que todos los terminadores son intrínsecos.
- Considerar el terminador como un único nucleótido en lugar de una región.

## 11. Referencias
- Terminación de la transcripción. *Biology Online*: https://www.biologyonline.com/dictionary/termination
- O'Neill et al., 2020. *Mechanisms of bacterial transcription termination*. Trends in Microbiology. https://doi.org/10.1016/j.tim.2020.02.002

## 12. Useful links
- Terminator (Wikipedia): https://en.wikipedia.org/wiki/Terminator_(genetics)
- RegulonDB: Ejemplos de terminadores https://regulondb.ccg.unam.mx

## 13. Historial del concepto
- La identificación de terminadores intrínsecos se estableció inicialmente mediante predicción de estructuras secundarias.
- Con el tiempo, se reconoció la importancia de los terminadores dependientes de Rho.
- RegulonDB incorpora ambos tipos cuando existe evidencia experimental o computacional sólida.

---

# Transcription Unit (TU) — Unidad Transcripcional

## 2. Definición simple
Una **unidad transcripcional (TU)** es un segmento del ADN que se transcribe como una sola molécula de RNA, iniciando en un **promotor** específico y terminando en un **terminador** específico.

## 3. Definición extendida
En RegulonDB, una **TU** se define como la región del genoma transcrita por la ARN polimerasa a partir de un promotor identificado y que finaliza en un terminador anotado. Una TU puede incluir:
- uno o varios genes (monocistrónica o policistrónica),
- regiones UTR 5’ y 3’,
- elementos intergénicos,
- sRNAs,
- e incluso terminadores internos cuando existe evidencia de readthrough.

Un mismo operón puede dar lugar a **múltiples TUs**, dependiendo de qué promotor(es) se utilicen y de si existen terminadores alternativos. La TU representa la **unidad funcional de expresión transcripcional**, a diferencia del gen, que es una unidad informacional.

## 4. Acrónimos y sinónimos relevantes
- TU
- transcription unit
- unidad transcripcional
- transcrito primario (no recomendado como sinónimo estricto)

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| TU name | nombre asignado según convención RegulonDB | sí | thrLABC-TU1 |
| promoter(s) | promotor(es) que inician la TU | sí | thrLp |
| terminator(s) | terminador(es) donde finaliza la TU | sí | thrLt |
| genes | genes contenidos en la TU | sí | thrL, thrA, thrB, thrC |
| strand | hebra donde se transcribe la TU | sí | forward |
| operon | operón al que pertenece la TU | no | thrLABC |

## 6. Representación gráfica del objeto
En RegulonDB, la TU aparece como una **flecha larga** que se extiende desde su promotor hasta su terminador. Las TUs de un mismo operón pueden visualizarse como flechas paralelas o superpuestas, mostrando las variantes transcripcionales.

![](./images/tu.png)

## 7. Comments (Notas importantes)
- Una TU puede ser **monocistrónica** (un solo gene) o **policistrónica** (varios genes).
- Un mismo gene puede aparecer en **múltiples TUs**, dependiendo de los promotores alternativos.
- La TU es la **unidad funcional** sobre la cual actúan la mayoría de los mecanismos regulatorios.
- Las TUs pueden cambiar con nueva evidencia experimental que redefina sus promotores o terminadores.
- En operones complejos, la existencia de terminadores internos crea TUs parciales.

## 8. Ejemplos

**Ejemplo simple:** TU monocistrónica que expresa únicamente un sRNA.

**Ejemplo policistrónico:** TU del operón *lacZYA*, que incluye tres genes.

**Ejemplo complejo:** Operón *thrLABC*, con múltiples TUs derivadas de promotores alternativos y terminadores compartidos.

## 9. Conexiones conceptuales
- **Promoter → TU → Terminator:** forma la unidad básica de transcripción.
- **TU → Operon:** un operón puede contener varias TUs.
- **TU → Genes:** define qué genes se expresan juntos.
- **TU y Regulación:** activadores y represores actúan sobre el promotor y, por extensión, sobre la TU.

## 10. Errores comunes
- Confundir TU con operón.
- Asumir que un gen pertenece a una sola TU.
- Pensar que todas las TUs se expresan necesariamente de forma continua.
- Igualar TU con “lo que se observa en RNA-seq”; RegulonDB usa evidencia curada específica.

## 11. Referencias
- Browning & Busby. 2004. *The regulation of bacterial transcription initiation*. Nature Reviews Microbiology. https://doi.org/10.1038/nrmicro820
- Cho et al. 2014. *Transcription unit architecture in bacteria*. Microbiology Spectrum. https://doi.org/10.1128/microbiolspec.MDNA3-0012-2014

## 12. Useful links
- Wikipedia – Transcription unit: https://en.wikipedia.org/wiki/Transcription_unit
- Biology Online – Transcription unit: https://www.biologyonline.com/dictionary/transcription-unit
- RegulonDB – Lista de TUs: https://regulondb.ccg.unam.mx/

## 13. Historial del concepto
- En definiciones clásicas, una TU se describía simplemente como “uno o más genes transcritos juntos”.
- Con evidencia moderna (TSS, terminadores, RNA-seq), la definición pasó a ser una entidad basada en evidencia experimental precisa.
- RegulonDB adoptó el modelo de múltiples TUs por operón para reflejar la complejidad real de la transcripción bacteriana.



---

# Operon (Operón)

## 2. Definición simple
Un **operón** es un conjunto de uno o más genes consecutivos en la misma hebra del ADN que pueden transcribirse coordinadamente como parte de una o más unidades transcripcionales (TUs).

## 3. Definición extendida
En RegulonDB, un **operón** es una entidad genómica compuesta por genes contiguos orientados en la misma hebra y que están funcionalmente relacionados. Estos genes pueden ser expresados por una o varias **unidades transcripcionales (TUs)** iniciadas desde promotores asociados al operón.

A diferencia de definiciones clásicas, un operón puede contener **múltiples TUs**, debido a la presencia de:
- promotores alternativos,
- terminadores internos,
- regulación diferencial dependiente de condiciones.

El operón es por lo tanto una estructura **genómica y organizacional**, mientras que la TU es una estructura **transcripcional**.

## 4. Acrónimos y sinónimos relevantes
- operon
- operón
- transcriptional cluster (término histórico, no recomendado)

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| operon name | nombre del operón | sí | thrLABC |
| genes | genes consecutivos en la misma hebra | sí | thrL, thrA, thrB, thrC |
| strand | hebra en la que están los genes | sí | forward |
| TUs | unidades transcripcionales asociadas | sí | thrLABC-TU1, thrLABC-TU2 |
| first gene | primer gen del operón | sí | thrL |

## 6. Representación gráfica del objeto
En RegulonDB, el operón aparece como un marco o región que contiene los genes orientados en la misma dirección. Debajo o encima se representan las **TUs**, que pueden depender de diferentes promotores y terminadores. Los promotores y terminadores se muestran como símbolos específicos conectados a las TUs.

Los operones complejos muestran múltiples TUs superpuestas, reflejando su arquitectura transcripcional real.

## 7. Comments (Notas importantes)
- Un operón puede tener **uno o múltiples promotores**.
- Un operón puede tener **uno o múltiples terminadores**, incluso **internos**.
- Un operón puede contener **varias TUs**, que expresan distintos subconjuntos de genes.
- El operón NO es equivalente a un regulón.
- Un operón no garantiza que todos sus genes se expresen juntos en todas las condiciones.

## 8. Ejemplos
**Ejemplo simple:** Operón monocistrónico con un solo gen, un promotor y un terminador.

**Ejemplo clásico:** Operón *lacZYA*, con tres genes regulados juntos bajo el control del represor LacI.

**Ejemplo complejo:** Operón *thrLABC*, con múltiples promotores, terminadores internos y varias TUs alternativas.

## 9. Conexiones conceptuales
- **Operon → Genes:** conjunto de genes consecutivos y orientados.
- **Operon → TUs:** puede originar múltiples unidades transcripcionales.
- **Operon → Regulación:** los factores reguladores actúan sobre los promotores que controlan las TUs del operón.
- **Operon ≠ TUs:** una TU es un transcrito, el operón es una organización genómica.
- **Operon ≠ Regulon:** un regulón es un conjunto de genes regulados por un mismo TF.

## 10. Errores comunes
- Asumir que un operón tiene una sola TU.
- Pensar que todos los genes del operón siempre se expresan juntos.
- Confundir operón con regulón.
- Interpretar que el operón termina automáticamente después del último gen (puede haber terminadores externos o internos).

## 11. Referencias
- Jacob F. & Monod J., 1961. *Genetic regulatory mechanisms in the synthesis of proteins*. Journal of Molecular Biology. https://doi.org/10.1016/S0022-2836(61)80072-7
- Browning & Busby. 2004. *The regulation of bacterial transcription initiation*. Nature Reviews Microbiology.

## 12. Useful links
- Operon (Wikipedia): https://en.wikipedia.org/wiki/Operon
- Biology Online – Operon: https://www.biologyonline.com/dictionary/operon
- RegulonDB – Lista de operones: https://regulondb.ccg.unam.mx

## 13. Historial del concepto
- En su definición original por Jacob y Monod, un operón representaba un conjunto de genes transcritos juntos.
- Con evidencia moderna (TSS, terminadores, RNA-seq), se reconoce que los operones pueden tener **múltiples TUs**.
- RegulonDB expandió el concepto para capturar operones complejos con promotores alternativos y terminadores internos.


---- 
A revisar porque fue generada por IA basada en el contexto de los articulos de regulonDB y definicions de Citlalli, tomando las colecciones de RegulonDB de mongo.
---- 

# Regulatory Interaction (Interacción Regulatoria)

## 2. Definición simple
Una **interacción regulatoria** es la relación entre un regulador activo y una entidad regulada, donde el regulador modifica la transcripción (activación, represión o efecto dual).

## 3. Definición extendida
En RegulonDB, una **regulatory interaction** representa el vínculo causal curado entre una conformación reguladora activa (por ejemplo, un TF o complejo regulador) y un objetivo regulado (promotor, TU, operón o gen, según el contexto curado). La interacción se caracteriza por una función regulatoria, dirección y soporte de evidencia.

Siguiendo el marco conceptual actualizado de RegulonDB, las interacciones regulatorias se separan de la definición estructural del promotor y se describen como relaciones funcionales entre entidades regulatorias y entidades reguladas.

## 4. Acrónimos y sinónimos relevantes
- regulatory interaction
- RI
- interacción TF-objetivo (uso informal)

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| active conformation | forma activa del regulador que ejecuta la interacción | sí | RhaS-L-rhamnose |
| regulatory function | efecto sobre la transcripción | sí | activator |
| regulated entity name | nombre de la entidad regulada | sí | rhaBAD promoter |
| regulated entity type | tipo de entidad regulada | sí | promoter |
| distance to promoter/first gene | distancia reportada en la interfaz de regulón | no | -61 |
| RBS coordinates | coordenadas del sitio de unión regulatorio (si disponible) | no | 112345-112360 |

## 6. Representación gráfica del objeto



## 7. Comments (Notas importantes)
- Una interacción no es equivalente a un sitio de unión aislado.
- La existencia de unión (binding) no siempre implica regulación funcional.
- Una misma conformación activa puede participar en múltiples interacciones.

## 8. Ejemplos
**Ejemplo simple:** un regulador activo reprime un promotor específico.

**Ejemplo complejo:** una misma conformación activa regula distintos promotores con funciones diferentes según condición.

## 9. Conexiones conceptuales
- **Regulatory interaction ↔ Regulator:** requiere un regulador/conformación activa.
- **Regulatory interaction ↔ Binding site:** puede estar respaldada por uno o más sitios.
- **Regulatory interaction → Regulon:** las interacciones definen el alcance del regulón.

## 10. Errores comunes
- Confundir unión física con regulación validada.
- Asumir que toda interacción aplica a todas las condiciones de crecimiento.
- Tratar interacción y regulón como sinónimos.

## 11. Referencias
- Mejía-Almonte C, et al. 2020. *Redefining fundamental concepts of transcription initiation in bacteria*. Nat Rev Genet. https://doi.org/10.1038/s41576-020-0254-8
- Tierrafría VH, et al. 2022. *RegulonDB 11.0*. Microbial Genomics. https://doi.org/10.1099/mgen.0.000833

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- Regulon search guide (repo): ../01_search_browse/regulon_search.md

## 13. Historial del concepto
- En modelos clásicos se describía de forma implícita dentro de promotores/operones.
- En marcos actuales se formaliza como relación regulador-objetivo con evidencia.

---

# Transcription Factor Binding Site (TFBS)

## 2. Definición simple
Un **binding site** es una región de ADN reconocida por un regulador, como un factor de transcripción o una holoenzima con sigma.

## 3. Definición extendida
En RegulonDB, un **binding site** es una secuencia genómica donde una molécula reguladora se une de forma específica o preferencial. Para TFs, suele distinguirse entre:
- **TFBS** (transcription factor binding site): sitio con evidencia de unión.
- **TFRS** (transcription factor regulatory site): subconjunto de TFBS con evidencia funcional de cambio regulatorio.

El marco conceptual de RegulonDB separa los sitios regulatorios de la definición del promotor: no todo sitio de unión forma parte estructural del promotor ni toda unión implica efecto regulatorio.

## 4. Acrónimos y sinónimos relevantes
- binding site
- TFBS
- TFRS
- regulatory site

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| left position | inicio del sitio en el genoma | sí | 345210 |
| right position | fin del sitio en el genoma | sí | 345225 |
| strand | hebra del ADN | sí | reverse |
| sequence | secuencia del sitio | no | TTGACATTTAGTAA |
| regulator/conformation | entidad que reconoce el sitio | sí | CRP-cAMP |
| evidence type | tipo de evidencia (binding/regulatory) | no | ChIP-seq |

## 6. Representación gráfica del objeto
En RegulonDB se representa como una marca corta sobre el ADN, asociada al regulador. En vistas de red, se expresa como parte del soporte de una interacción regulatoria.

## 7. Comments (Notas importantes)
- Un TFBS puede no ser un TFRS.
- Sitios intragénicos pueden ser funcionales o no funcionales.
- El contexto experimental condiciona su interpretación.

## 8. Ejemplos
**Ejemplo simple:** sitio upstream de un promotor reconocido por un activador.

**Ejemplo complejo:** sitio intragénico con evidencia de unión sin efecto claro en expresión.

## 9. Conexiones conceptuales
- **Binding site ↔ TF/sigma factor:** define reconocimiento molecular.
- **Binding site ↔ Regulatory interaction:** soporte físico potencial.
- **Binding site ≠ Promoter:** conceptos relacionados pero no equivalentes.

## 10. Errores comunes
- Llamar regulatorio a cualquier sitio de unión.
- Asumir que todo sitio está en región intergénica.
- Igualar sitio de unión con promotor completo.

## 11. Referencias
- Mejía-Almonte C, et al. 2020. *Redefining fundamental concepts of transcription initiation in bacteria*. https://doi.org/10.1038/s41576-020-0254-8
- Tierrafría VH, et al. 2022. *RegulonDB 11.0*. https://doi.org/10.1099/mgen.0.000833

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- Sequence Ontology: http://www.sequenceontology.org

## 13. Historial del concepto
- Inicialmente se usó como sinónimo funcional de control regulatorio.
- Actualmente se diferencia explícitamente unión física y efecto regulatorio.

---

# Regulon (Regulón)

## 2. Definición simple
Un **regulón** es el conjunto de entidades reguladas por un mismo regulador o por una misma conformación reguladora activa.

## 3. Definición extendida
En RegulonDB, un **regulon** agrupa genes, unidades transcripcionales, promotores u operones bajo control de una entidad reguladora común en un nivel de regulación específico (aquí, principalmente transcripcional). El criterio de pertenencia está definido por interacciones regulatorias curadas, no por proximidad genómica.

En este sentido, un regulón no equivale a operón ni a TU: cruza distintas regiones del genoma y puede incluir blancos heterogéneos.

## 4. Acrónimos y sinónimos relevantes
- regulon
- regulón
- TF regulon

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| regulator name | regulador que define el regulón | sí | TrpR |
| regulator type | tipo de regulador | sí | transcription factor |
| regulated genes count | número de genes regulados | no | 34 |
| regulated operons count | número de operones regulados | no | 12 |
| regulated TUs count | número de TUs reguladas | no | 18 |
| regulatory interactions count | número de interacciones regulatorias | no | 42 |

## 6. Representación gráfica del objeto
En RegulonDB se visualiza como una red centrada en un regulador con múltiples blancos distribuidos en el genoma.

## 7. Comments (Notas importantes)
- Un regulón puede incluir entidades no contiguas.
- Un gen puede pertenecer a varios regulones.
- El tamaño del regulón depende de evidencia y condiciones curadas.

## 8. Ejemplos
**Ejemplo simple:** regulón de un regulador con pocos promotores blanco.

**Ejemplo complejo:** regulón global con decenas de genes y funciones mixtas.

## 9. Conexiones conceptuales
- **Regulon ↔ Regulatory interactions:** el regulón emerge de estas interacciones.
- **Regulon ≠ Operon:** operón es organización local; regulón es control distribuido.
- **Regulon ↔ GENSOR Unit:** puede mapearse a respuestas sistémicas.

## 10. Errores comunes
- Confundir regulón con operón.
- Asumir un único modo regulatorio para todos los blancos.
- Ignorar conformaciones activas/inactivas del regulador.

## 11. Referencias
- Mejía-Almonte C, et al. 2020. *Redefining fundamental concepts of transcription initiation in bacteria*. https://doi.org/10.1038/s41576-020-0254-8
- Salgado H, et al. RegulonDB resources (varias versiones).

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- Regulon search guide (repo): ../01_search_browse/regulon_search.md

## 13. Historial del concepto
- Originalmente asociado casi exclusivamente a genes controlados por un TF.
- Se amplió para reflejar blancos múltiples, tipos de entidades reguladas y estados regulatorios.

---

# Transcription Factor (Factor de Transcripción)

## 2. Definición simple
Un **factor de transcripción (TF)** es un regulador que modifica la transcripción al reconocer sitios específicos en el ADN.

## 3. Definición extendida
En RegulonDB, un **transcription factor** es una entidad reguladora (usualmente proteica, pero no limitada a una sola arquitectura) capaz de activar, reprimir o modular transcripción mediante unión a regiones regulatorias y/o interacción con la maquinaria de transcripción.

Un TF puede presentar diferentes conformaciones funcionales (por ejemplo, libre, unido a efector, complejo activo/inactivo), lo cual determina su función regulatoria en condiciones específicas.

## 4. Acrónimos y sinónimos relevantes
- TF
- transcription factor
- regulador transcripcional

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| _id | identificador único en RegulonDB | sí | RDBECOLITFC00001 |
| name | nombre completo del regulador | sí | DNA-binding transcriptional repressor ExuR |
| abbreviatedName | nombre corto | sí | ExuR |
| type | clase de regulador | sí | transcriptionFactor |
| regulationType | tipo de regulación asociada | no | Transcription-Factor-Binding |
| conformations | conformaciones asociadas (producto/complejo) | no | active, inactive |

## 6. Representación gráfica del objeto
En redes de RegulonDB, el TF se representa como nodo regulador conectado con sus blancos y, cuando aplica, con complejos/conformaciones activas.

## 7. Comments (Notas importantes)
- No toda proteína que une ADN es necesariamente regulador funcional en todas las condiciones.
- La función puede cambiar según efector, estado oligomérico o complejación.
- Un TF puede participar en múltiples regulones.

## 8. Ejemplos
**Ejemplo simple:** represor que bloquea el acceso de RNAP.

**Ejemplo complejo:** regulador dual con activación de algunos promotores y represión de otros.

## 9. Conexiones conceptuales
- **TF ↔ Binding site:** reconocimiento de secuencia objetivo.
- **TF ↔ Regulatory interaction:** define función sobre blancos.
- **TF ↔ Regulon:** determina el conjunto regulado.

## 10. Errores comunes
- Asumir que TF implica siempre proteína monomérica.
- Igualar presencia de unión con cambio de expresión.
- Ignorar la importancia de conformaciones activas.

## 11. Referencias
- Mejía-Almonte C, et al. 2020. *Redefining fundamental concepts of transcription initiation in bacteria*. https://doi.org/10.1038/s41576-020-0254-8
- Tierrafría VH, et al. 2022. *RegulonDB 11.0*. https://doi.org/10.1099/mgen.0.000833

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- Transcription factor (Wikipedia): https://en.wikipedia.org/wiki/Transcription_factor

## 13. Historial del concepto
- El concepto clásico enfatizaba activadores/represores proteicos.
- Se formalizó con mayor precisión sobre estados conformacionales y evidencia funcional.

---

# Regulatory Complexes (Complejos Regulatorios)

## 2. Definición simple
Un **complejo regulatorio** es una entidad formada por uno o más componentes moleculares que actúa como unidad funcional en regulación génica.

## 3. Definición extendida
En RegulonDB, los **regulatory complexes** incluyen complejos activos o inactivos que pueden estar compuestos por proteínas reguladoras y, en ciertos casos, efectores pequeños. Estos complejos definen el estado funcional real de la regulación (por ejemplo, unión/ausencia de cofactor).

Los complejos reguladores son clave para representar cambio de función entre conformaciones y para conectar señales ambientales con control transcripcional.

## 4. Acrónimos y sinónimos relevantes
- regulatory complex
- complex conformation
- complejo activo/inactivo

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| _id | identificador del complejo | sí | RDBECOLIRCC00004 |
| name | nombre del complejo | no | RhaS-L-rhamnose DNA-binding transcriptional activator |
| type | estado funcional del complejo | sí | active |
| products | componentes (productos) del complejo | sí | RDBECOLIPDC03926 |
| regulatoryContinuants_ids | efectores/cofactores regulatorios asociados | no | RDBECOLICNC00069 |
| organisms_id | organismo asociado | sí | RDBECOLIORC00001 |

## 6. Representación gráfica del objeto
En RegulonDB, se representa como estado/conformación del regulador, enlazado a sus componentes y a las interacciones regulatorias correspondientes.

## 7. Comments (Notas importantes)
- Un mismo regulador puede tener más de un complejo funcional.
- El estado activo/inactivo depende del contexto molecular.
- No todo complejo con unión molecular implica regulación efectiva en todas las condiciones.

## 8. Ejemplos
**Ejemplo simple:** regulador unido a su efector que activa transcripción.

**Ejemplo complejo:** regulador con estados activo e inactivo según metabolito.

## 9. Conexiones conceptuales
- **Regulatory complex ↔ TF:** representa conformación funcional.
- **Regulatory complex ↔ Regulatory interaction:** define qué estado ejecuta la interacción.
- **Regulatory complex ↔ Regulatory continuant:** integra señales químicas.

## 10. Errores comunes
- Tratar complejo y regulador como idénticos sin estados.
- Ignorar componentes no proteicos del estado regulatorio.
- Asumir que solo existe conformación activa.

## 11. Referencias
- Tierrafría VH, et al. 2022. *RegulonDB 11.0*. https://doi.org/10.1099/mgen.0.000833
- RegulonDB / EcoCyc curation framework.

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- EcoCyc: https://ecocyc.org

## 13. Historial del concepto
- Inicialmente se documentaban principalmente reguladores “libres”.
- Se consolidó la representación explícita de conformaciones y complejos en curación moderna.

---

# Sigma Factor (Factor sigma)

## 2. Definición simple
Un **factor sigma** es la subunidad de especificidad de la ARN polimerasa que dirige el reconocimiento de promotores.

## 3. Definición extendida
En RegulonDB y en el marco conceptual actualizado, un **sigma factor** forma parte de la holoenzima RNAP (E sigma) y determina subconjuntos de promotores reconocidos en función de condiciones celulares. Bacterias como *E. coli* poseen familias sigma (por ejemplo sigma70 y sigma54) y factores alternativos que redistribuyen programas transcripcionales.

El sigma no solo participa en reconocimiento basal de elementos promotores, también condiciona arquitectura de promotores y respuestas globales.

## 4. Acrónimos y sinónimos relevantes
- sigma factor
- sigma
- factor sigma
- RpoX (según gen)

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| _id | identificador en RegulonDB | sí | RDBECOLISFC00001 |
| name | nombre completo | sí | RNA polymerase sigma factor FliA |
| abbreviatedName | nombre corto | sí | sigma28 |
| genes_id | gen que codifica el sigma | sí | RDBECOLIGNC01323 |
| synonyms | nombres alternativos | no | RpoF, sigma 28 |
| organisms_id | organismo asociado | sí | RDBECOLIORC00001 |

## 6. Representación gráfica del objeto
En diagramas funcionales aparece asociado a RNAP holoenzima y a clases de promotores que reconoce.

## 7. Comments (Notas importantes)
- Un sigma define programas transcripcionales dependientes de condición.
- Distintos sigma pueden iniciar en el mismo TSS y definir promotores distintos.
- La competencia entre sigma afecta expresión global.

## 8. Ejemplos
**Ejemplo simple:** sigma70 en promotores housekeeping.

**Ejemplo complejo:** sigma alternativos (sigma28, sigma54, sigma38) con regulones especializados.

## 9. Conexiones conceptuales
- **Sigma factor ↔ Promoter:** reconocimiento de elementos promotores.
- **Sigma factor ↔ RNAP core:** formación de E sigma.
- **Sigma factor ↔ Regulon/Sigmulon:** conjuntos de genes bajo su control.

## 10. Errores comunes
- Considerar sigma como TF clásico de sitio fijo.
- Asumir que cada promotor tiene un único sigma posible.
- Ignorar sigma alternativos en respuestas ambientales.

## 11. Referencias
- Mejía-Almonte C, et al. 2020. *Redefining fundamental concepts of transcription initiation in bacteria*. https://doi.org/10.1038/s41576-020-0254-8
- Tierrafría VH, et al. 2022. *RegulonDB 11.0*. https://doi.org/10.1099/mgen.0.000833

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- Sigma factor (Wikipedia): https://en.wikipedia.org/wiki/Sigma_factor

## 13. Historial del concepto
- Se pasó de una visión centrada en sigma70 a una visión multsigma dependiente de contexto.
- La curación moderna distingue familias sigma y su impacto regulatorio específico.

---

# GENSOR Unit (GU)

## 2. Definición simple
Una **GENSOR Unit (GU)** es una unidad conceptual que integra regulación genética y respuesta funcional en red.

## 3. Definición extendida
En RegulonDB, **GU (GENetic SENsory Response Unit)** conecta un regulador, sus interacciones regulatorias y las consecuencias funcionales aguas abajo (genes, productos y procesos). Sirve para representar cómo una señal se traduce en una respuesta fisiológica coordinada.

La GU no reemplaza entidades básicas (gen, promotor, TU, operón, regulón), sino que las integra en una capa sistémica para interpretación funcional.

## 4. Acrónimos y sinónimos relevantes
- GU
- GENSOR Unit
- Genetic Sensory Response Unit

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| name | nombre de la GU | no |  |
| regulator(s) | regulador(es) centrales | no |  |
| regulated entities | genes/TUs/operones integrados | no |  |
| functional outcome | proceso o respuesta asociada | no |  |
| supporting interactions | interacciones regulatorias vinculadas | no |  |
| evidence/references | soporte documental | no |  |

## 6. Representación gráfica del objeto
En RegulonDB, una GU suele representarse como un diagrama funcional que conecta regulación, genes objetivo, rutas y efecto fisiológico.

## 7. Comments (Notas importantes)
- Se usa para integrar conocimiento curado en una vista funcional.
- Puede abarcar varios niveles de organización biológica.
- Su granularidad depende de la disponibilidad de evidencia.

## 8. Ejemplos
**Ejemplo simple:** GU centrada en un regulador y una ruta metabólica principal.

**Ejemplo complejo:** GU que integra múltiples ramas funcionales y regulación combinatoria.

## 9. Conexiones conceptuales
- **GU ↔ Regulon:** usa regulones como módulo de entrada.
- **GU ↔ Metabolic/functional context:** conecta regulación con fenotipo.
- **GU ≠ Regulon:** regulón es conjunto regulado; GU incluye respuesta funcional.

## 10. Errores comunes
- Usar GU como sinónimo de regulón.
- Asumir que toda GU representa una sola vía lineal.
- Ignorar que es una capa integrativa, no solo transcripcional.

## 11. Referencias
- RegulonDB documentation and GENSOR framework resources.
- Mejía-Almonte C, et al. 2020. https://doi.org/10.1038/s41576-020-0254-8

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- Standards in this repo: ../07_technical_reference/standards_ontologies.md

## 13. Historial del concepto
- Fue introducido para integrar regulación y función en modelos de sistema.
- Ha evolucionado como recurso visual y conceptual dentro de RegulonDB.

---

# sRNA (small RNA / RNA pequeño)

## 2. Definición simple
Un **sRNA** es un RNA pequeño no codificante que regula la expresión génica, generalmente a nivel postranscripcional.

## 3. Definición extendida
En RegulonDB, un **sRNA** es una entidad reguladora de tipo RNA (frecuentemente anotada como `small RNA`) que modula estabilidad y/o traducción de mRNAs blanco, muchas veces con ayuda de chaperonas como Hfq. Algunos sRNAs participan también en redes transcripcionales al afectar reguladores.

La curación distingue el sRNA como regulador funcional y no como simple intermediario de expresión.

## 4. Acrónimos y sinónimos relevantes
- sRNA
- small RNA
- small regulatory RNA
- ncRNA (relacionado, más amplio)

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| _id | identificador en RegulonDB | sí | RDBECOLI... |
| name | nombre del sRNA | sí | CyaR |
| type | tipo de regulador | sí | small RNA |
| synonyms | nombres alternativos | no | ryeE |
| note | descripción funcional curada | no | regula degradación de ompX |
| confidenceLevel | nivel de confianza curatorial | no | W |

## 6. Representación gráfica del objeto
En redes regulatorias se representa como nodo RNA regulador conectado a sus genes/transcritos objetivo.

## 7. Comments (Notas importantes)
- Muchos sRNAs requieren proteínas accesorias (por ejemplo Hfq).
- Un sRNA puede tener múltiples blancos.
- Su efecto puede depender de condición y contexto celular.

## 8. Ejemplos
**Ejemplo simple:** sRNA que reprime traducción de un mRNA de membrana.

**Ejemplo complejo:** sRNA con múltiples blancos y competencia por Hfq.

## 9. Conexiones conceptuales
- **sRNA ↔ Target mRNA:** regulación postranscripcional.
- **sRNA ↔ Regulatory network:** puede modular reguladores globales.
- **sRNA ↔ Product concept:** es producto funcional RNA.

## 10. Errores comunes
- Tratar todos los RNAs pequeños como equivalentes funcionales.
- Asumir que su acción siempre es represión.
- Omitir dependencia de proteínas chaperonas.

## 11. Referencias
- Tierrafría VH, et al. 2022. *RegulonDB 11.0*. https://doi.org/10.1099/mgen.0.000833
- RegulonDB curated regulator notes for small RNAs.

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- sRNA (Wikipedia): https://en.wikipedia.org/wiki/Small_RNA

## 13. Historial del concepto
- Inicialmente se documentaban pocos sRNAs con blancos puntuales.
- Con evidencia de alto rendimiento y curación continua se expandió su cobertura en redes regulatorias.

---


# Effector (Efector)

## 2. Definición simple
Un **efector** es una molécula que modifica la actividad de un regulador al unirse a él, cambiando su estado funcional.

## 3. Definición extendida
En RegulonDB, un **effector** es típicamente una molécula pequeña (por ejemplo, metabolito, nucleótido o ion) que altera la conformación o la capacidad regulatoria de un factor de transcripción o complejo regulatorio. Su unión puede activar, inhibir o modular afinidad por ADN, especificidad de blanco o función regulatoria final.

El efector no es, por sí mismo, el regulador transcripcional principal; actúa como señal molecular que conecta el estado fisiológico con la respuesta regulatoria.

## 4. Acrónimos y sinónimos relevantes
- effector
- coregulator (en algunos contextos)
- small-molecule effector
- molécula efectora

## 5. Propiedades mínimas del objeto
| Propiedad | Descripción | Requerida | Ejemplo |
|-----------|-------------|-----------|---------|
| _id | identificador de la molécula en base de datos | sí | RDBECOLICNC00069 |
| name | nombre del efector | sí | L-rhamnose |
| type | tipo químico/funcional | sí | metabolite |
| synonyms | nombres alternativos | no | rhamnose |
| associated regulator/complex | regulador o complejo modulado | no | RhaS-L-rhamnose |
| functional effect | efecto regulatorio reportado | no | activation |

## 6. Representación gráfica del objeto
En RegulonDB, los efectores suelen aparecer asociados a conformaciones regulatorias o complejos (por ejemplo, `Regulator-effector`) que representan estados activos o inactivos.

## 7. Comments (Notas importantes)
- Un mismo regulador puede responder a distintos efectores.
- El efecto del efector depende del contexto fisiológico y de concentración.
- No todo ligando reportado implica cambio regulatorio funcional confirmado.

## 8. Ejemplos
**Ejemplo simple:** una molécula que activa un regulador al promover su conformación activa.

**Ejemplo complejo:** una molécula que cambia selectivamente función activadora/represora según promotor.

## 9. Conexiones conceptuales
- **Effector ↔ Regulatory complex:** define estados activo/inactivo de complejos.
- **Effector ↔ Transcription factor:** modula afinidad por ADN o función regulatoria.
- **Effector ↔ Regulatory interaction:** condiciona si una interacción ocurre o cambia de signo.

## 10. Errores comunes
- Confundir efector con regulador principal.
- Asumir que todo efector siempre activa.
- Ignorar dependencia de condición experimental para observar efecto.

## 11. Referencias
- Mejía-Almonte C, et al. 2020. *Redefining fundamental concepts of transcription initiation in bacteria*. https://doi.org/10.1038/s41576-020-0254-8
- Tierrafría VH, et al. 2022. *RegulonDB 11.0*. https://doi.org/10.1099/mgen.0.000833

## 12. Useful links
- RegulonDB: https://regulondb.ccg.unam.mx
- EcoCyc (ligandos/regulación): https://ecocyc.org

## 13. Historial del concepto
- En definiciones clásicas, el rol del efector se describía de forma implícita dentro de regulación por TFs.
- En modelos actuales, se explicita su papel como modulador de conformaciones y estado regulatorio.

---
