# Plan de trabajo: cambio de licencia a CC BY 4.0 y brechas de la documentación

- **Fecha:** 2026-11-18
- **Estado:** Licencia decidida el 2026-11-18 (CC BY-NC 4.0, ver sección 0). Las secciones 1–6 son el análisis original, que proponía CC BY 4.0.
- **Alcance:** carpeta `regulondb-docs` (todas las secciones) y el borrador de solicitud GCBR en Google Drive (`GCBRS-Application.docx`).

---

## 0. Decisión adoptada (2026-11-18): CC BY-NC 4.0

El equipo decidió que RegulonDB usará **Creative Commons Attribution–NonCommercial 4.0 International (CC BY-NC 4.0)** para sus datos y su documentación; el software se mantiene bajo MIT. Esta decisión **reemplaza la propuesta de CC BY 4.0** de las secciones siguientes, que se conservan como antecedente.

### Cambios ya aplicados en la documentación

| Archivo | Cambio |
|---|---|
| `00_about_policies/license.md` | Versión 1.1: CC BY-NC 4.0 (datos), MIT (software), uso comercial con acuerdo aparte; cita principal corregida; peticiones de atribución y enlace como buenas prácticas |
| `00_about_policies/fair_policy.md` | CC BY-SA 4.0 → CC BY-NC 4.0 |
| `README.md`, `CONTRIBUTING.md` | Documentación: CC BY-SA 4.0 → CC BY-NC 4.0 |
| `00_about_policies/terms_conditions.md` | EULA de 2006 retirado (movido a `to_delete/2026-11-18/`) y quitado del índice, del menú (`SUMMARY.md`) y del portal (`docs.config.json`) |

### Pendientes fuera de este repositorio (equipo de software)

1. **Cabecera de los archivos descargables.** Los 24 archivos de `downloadableFilesDatamart` llevan en el campo `license` el texto tipo EULA (*"RegulonDB is free for academic/noncommercial use. User is not entitled to change or erase data sets…"*), que contradice CC BY-NC 4.0 (que permite adaptar). Texto sugerido:

   ```
   # RegulonDB <versión> (<fecha>). Data licensed under CC BY-NC 4.0:
   # https://creativecommons.org/licenses/by-nc/4.0/
   # Commercial use requires a separate agreement: regulondb@ccg.unam.mx
   # Please cite: Salgado H et al. (2024) Nucleic Acids Res 52(D1):D255-D264. doi:10.1093/nar/gkad1072
   ```

2. **Zenodo.** El registro de RegulonDB v12.0.0 (doi:10.5281/zenodo.8346680) declara CC BY-NC-SA 4.0; cambiar a CC BY-NC 4.0 en ese registro y usar CC BY-NC 4.0 en los registros de releases nuevas (la 14.5.1 aún no está en Zenodo).
3. **Sitio web.** Revisar el pie de página y el enlace "Terms and conditions" de la portada, que apunta al EULA retirado.
4. **FAIRsharing y re3data.** Registrar la licencia CC BY-NC 4.0 (hoy el registro de FAIRsharing no muestra licencia).
5. **Repositorios de software.** Confirmar que los repos de `github.com/regulondbunam` tengan archivo `LICENSE` MIT.

### Implicaciones que conviene tener presentes

- **GCBR (pregunta 4d).** El documento de conceptos de GCBR pide licencias o términos de uso conformes con la *Open Definition*; una cláusula NC no se considera conforme. Conviene explicar en la respuesta 4d por qué se eligió NC y que el uso comercial está disponible mediante acuerdo.
- **Integraciones.** RNAcentral publica todo bajo CC0, y DSMZ D3 usa CC BY; para compartir datos con ellos hará falta un permiso o acuerdo específico que autorice su redistribución bajo esas licencias.

## 1. Resumen

1. **Hoy RegulonDB declara cuatro licencias distintas para sus datos**, y se contradicen entre sí:
   - CC BY-NC 4.0 en `license.md` y en la respuesta 4d de la solicitud GCBR.
   - CC BY-SA 4.0 en `fair_policy.md`.
   - El EULA académico de 2006 en `terms_conditions.md`, que prohíbe redistribuir, modificar e integrar los datos en otras bases.
   - La documentación, por su parte, se declara CC BY-SA 4.0.

   Antes de cualquier integración hay que unificar esto.
2. **Pasar los datos a CC BY 4.0 es coherente con D3 (DSMZ) y con GCBR.** El documento de conceptos de GCBR pide licencias o términos de uso conformes a la *Open Definition*, y una cláusula NC (no comercial) no cumple esa definición. Con CC BY, la respuesta 4d de la solicitud deja de ser un punto débil.
3. **RNAcentral es un caso aparte.** Publica todo bajo CC0, así que CC BY no basta para que pueda redistribuir nuestros datos. Hace falta decidir si se dedica a CC0 el subconjunto que se le envíe o si se firma un permiso explícito.
4. **Antes de cambiar la licencia hay que revisar los derechos de terceros.** RegulonDB importa en cada release anotaciones de EcoCyc (ver `credits.md`, línea 97), y EcoCyc tiene su propia licencia (SRI). Si esos datos se redistribuyen, la licencia de RegulonDB no puede ser más abierta que la de EcoCyc sin su permiso.
5. **La documentación tiene 38 archivos `.md` vacíos**, y la mayoría aparece en `SUMMARY.md`: todo `03_tools_visualizations`, `04_curation` (salvo el glosario y el índice), `06_tutorials_videos`, las notas de release y el historial de versiones. Varios de esos huecos coinciden con campos que siguen en blanco en la solicitud GCBR (3e i, 3e iii y 3b).

---

## 2. Fuentes revisadas

| Fuente | Qué se tomó |
|---|---|
| `regulondb-docs/` (224 archivos y el historial de git) | Inventario, declaraciones de licencia, archivos vacíos, navegación y metadatos de revisión |
| `docs/00`–`docs/09` (planes previos) | Estado declarado del trabajo GCBR (revisión del 2026-02-10) |
| Google Doc `GCBRS-Application.docx` (versión en Drive al 2026-11-18) | Estado de cada respuesta: completa, con problemas o en blanco |
| `context/global-biodata-info/*.pdf` | Criterio GCBR de licencia abierta (*Open Definition*) y pregunta 4d |
| Web: RNAcentral, BacDive/DSMZ y BioCyc/EcoCyc | Licencias de los socios y de la fuente de datos de terceros |

> Nota: la copia local `context/GCBRS-Application.docx` es del 2026-02-10 y probablemente esté desactualizada respecto a la de Drive. Conviene tomar la de Drive como versión vigente.

---

## 3. Hallazgos

### 3.1 Declaraciones de licencia actuales

| Archivo | Qué declara hoy | Problema frente a CC BY 4.0 |
|---|---|---|
| `00_about_policies/license.md` §1 | Datos bajo **CC BY-NC 4.0** | Hay que reemplazarla |
| `00_about_policies/license.md` §2 | El uso comercial requiere un acuerdo aparte | Con CC BY esta sección desaparece |
| `00_about_policies/license.md` §5 | Software bajo **MIT** | Se mantiene, pero hay que confirmar los `LICENSE` en GitHub |
| `00_about_policies/license.md` §6 | Pide atribución y enlaces directos a los objetos de RegulonDB | CC BY 4.0 (§2.a.5.B) prohíbe imponer condiciones adicionales. Debe redactarse como **solicitud** de buenas prácticas, no como condición |
| `00_about_policies/license.md` (formato) | Dos líneas "Last updated" y secciones 5–6 después del pie | Reordenar el texto y fijar versión y fecha |
| `00_about_policies/fair_policy.md` §5 | Datos bajo **CC BY-SA 4.0** | Contradice a `license.md` |
| `00_about_policies/terms_conditions.md` | **EULA v2.0 (2006)**: uso académico, sin redistribución, sin derivados, sin integración en otras bases, vigencia de un año, cita de v11.0 | Es incompatible con CC BY, con D3 y con RNAcentral. Hay que retirarlo o convertirlo en "Términos de uso del sitio" |
| `README.md` y `CONTRIBUTING.md` | Documentación bajo **CC BY-SA 4.0** | Decidir si se unifica a CC BY 4.0 |
| `00_about_policies/credits.md` línea 123 | Imagen de portada bajo CC BY-NC-SA 4.0 (Claire Rioualen) | Puede quedarse, pero conviene marcarla como excepción explícita |
| `00_about_policies/ethics_and_download_policy.md`, `README.md` de la sección | Remiten a "licencia clara" | Solo hay que revisar los enlaces |
| `00_about_policies/how_to_cite.md` | Guía de citación | Debe incluir el **texto de atribución CC BY** recomendado |
| `docs.config.json` | Incluye `license.md` y `terms_conditions.md` en el portal | Ajustar si `terms_conditions` se retira o se renombra |
| Solicitud GCBR, respuesta 4d | CC BY-NC 4.0, MIT y licencia comercial a petición | Reescribirla con la licencia nueva y su URL |

### 3.2 Condiciones previas y riesgos del cambio

1. **Titularidad y aprobación institucional.** El EULA afirma que RegulonDB es propiedad de la UNAM. Por eso el cambio de licencia necesita el visto bueno de la dirección del CCG y del área jurídica de la UNAM que corresponda, y no solo una decisión del grupo.
2. **Datos de terceros:**
   - **EcoCyc/BioCyc (SRI).** RegulonDB importa en cada release la anotación funcional y las coordenadas de genes y productos. Hay que verificar con SRI si esos campos pueden redistribuirse bajo CC BY. Si no, se pueden excluir de los productos CC BY o marcarlos con su propia licencia.
   - **Colección `publications`.** Revisar si guarda resúmenes (abstracts) de artículos, que tienen derechos de autor de las editoriales. Los metadatos bibliográficos no presentan problema.
   - **Datasets de alto rendimiento (HT)** derivados de GEO, SRA y ArrayExpress. Revisar las condiciones de origen, que en general son abiertas.
   - **Ontologías.** MCO es propia. Confirmar la licencia de GO y ECO para los términos que se redistribuyen en `terms` y `ontologies`.
   - **Imágenes y figuras** de la documentación y del sitio: identificar al autor y la licencia de cada una.
3. **Irrevocabilidad.** Las licencias CC no se pueden revocar sobre las copias ya distribuidas. Hay que definir desde qué release rige CC BY (por ejemplo, la próxima versión, o también todas las anteriores) y anunciarlo con fecha.
4. **RNAcentral (CC0).** Opciones:
   - (a) Dedicar a CC0 solo el subconjunto que se envíe (sRNA y sus anotaciones).
   - (b) Firmar un permiso o carta que autorice a RNAcentral a redistribuir bajo CC0.
   - (c) Preguntar a RNAcentral cómo manejan las bases expertas que son CC BY.

   La decisión es del equipo y de la UNAM.
5. **D3 (DSMZ).** CC BY es la misma licencia que usan sus bases (por ejemplo, BacDive). Hay que acordar con Lorenz Reimer el formato de atribución y los enlaces de vuelta a RegulonDB dentro de la ontología D3O.
6. **Sostenibilidad.** Con CC BY desaparece la vía de "licencia comercial". Revisar si alguna narrativa de financiamiento (respuesta 4a, `funding_credits.md`) o algún convenio vigente depende de ella.
7. **Lugares fuera de este repositorio** donde también aparece la licencia: pie y páginas del sitio web, página de descargas, cabeceras de los archivos TSV/JSON, respuestas o metadatos de la API GraphQL, imágenes Docker y dumps, registros de Zenodo, FAIRsharing, re3data e identifiers.org, los `README` y `LICENSE` de los repos en `github.com/regulondbunam` y futuros artículos.

### 3.3 Brechas de la documentación (aparte de la licencia)

**A. Archivos vacíos (0 bytes) que ya aparecen en la navegación**

| Sección | Archivos vacíos |
|---|---|
| `01_search_browse` | `catalog_navigation.md`, `collections.md`, `ontologies_mco.md` |
| `02_data_access/technical_resources/database_collections` | Los 7 archivos, que duplican a `07_technical_reference/collection_*` |
| `03_tools_visualizations` | Los 10 archivos, incluido el `README` |
| `04_curation` | `curation_workflow`, `classical_curation`, `ht_data_curation`, `curation_tools`, `evidence_classification`, `mco_usage_curation`, `quality_control`, `appendices` y `glossary.md` |
| `05_releases_updates` | `release_notes.md`, `version_history.md` |
| `06_tutorials_videos` | Los 7 archivos, incluido el `README` |

**B. Navegación y publicación**

- `SUMMARY.md` no enlaza:
  - `helpdesk-protocol.md`
  - `02_data_access/README.md` ni `technical_resources/README.md`
  - `search_overview.md` ni `operon_search.md`
  - 17 fichas `07_technical_reference/collection_*`
  - el glosario (`04_curation/glossary/glossary.md`)
  - toda la sección `06_tutorials_videos`
- `docs.config.json` solo publica "About" y el `README` de búsqueda. Las demás secciones no llegan al portal.
- `docs/README.md` no lista `06_`, `07_` ni `09_`, y no existe un `08_`.

**C. Duplicados y limpieza**

- `07_technical_reference/standards_ontologiest.md` tiene una errata en el nombre y duplica a `standards_ontologies.md`.
- `04_curation/glossary.md` está vacío y el glosario real vive en `glossary/glossary.md`.
- `Concepts-Citlalli-nihms-1650273.pdf` está repetido en la raíz y en `context/pdfs/`.
- Hay imágenes sueltas en `01_search_browse/` (`image*.png`).
- Varios `.DS_Store` están versionados en git.
- Queda la carpeta `to_delete/` pendiente de borrar.
- Hay un cambio sin confirmar en `04_curation/glossary/glossary.md`.

**D. Coherencia editorial**

- El glosario y `manual_index.md` están en español; el resto está en inglés. Hay que decidir el idioma del portal.
- No todas las páginas tienen "Last updated" ni responsable. Faltan, por ejemplo, en `01_`, `02_`, `about_us` y `terms_conditions`.

**E. Inconsistencias entre la documentación y la solicitud GCBR en Drive**

| Tema | Documentación | Solicitud en Drive | Acción |
|---|---|---|---|
| FTE 2023–2024 | Tabla con 8.65 (`staff_effort_fte.md`) | La tabla dice 8.65 y el texto dice 8.15 | Corregir el texto de la solicitud a 8.65 o justificar la diferencia |
| Distribución geográfica | No hay página pública (`geographic_usage.md` se planeó pero no existe) | 4.46 % frente a 7.73 % para el país sede; el top-10 suma alrededor de 101 % | Fijar una cifra validada, publicarla en la documentación y copiarla a la solicitud |
| Preservación | `data_preservation_policy.md` no menciona Zenodo | La respuesta 4c dice que se archiva en Zenodo con DOI | Alinear ambos textos |
| Financiamiento | `funding_credits.md`: NIH y CONACyT | La respuesta 1c menciona NSERC (Canadá) | Confirmar con el equipo y unificar |
| Documentación de curación (3e i) y versionado/QA (3e iii) | `04_curation` vacío; `release_notes` y `version_history` vacíos | En blanco | **Prioridad alta:** escribir estas páginas y citarlas en la solicitud |
| Volumen de datos (3b) | `database_collections_index.md` ya tiene volúmenes | En blanco | Reusar la tabla con el conteo por entidad y versión |
| Identificadores (3a) | Sin página de política de IDs (`identifier_policy.md` se planeó) | El registro en identifiers.org sigue pendiente | Escribir la página y registrar el prefijo |
| Licencia (4d) | Contradictoria (ver 3.1) | CC BY-NC | Resolver con la Fase 0 |

**F. Planes previos que quedaron desactualizados**

`docs/06_gcbr_traceability_matrix.md` sigue marcando como "Faltante" puntos que ya tienen página (3c, 4c, 5a, 5b, 1c y 1d), y marca 4d como "Completo" pese a la contradicción de licencias. Hay que actualizarlo al terminar este plan.

---

## 4. Plan de trabajo

Las duraciones son orientativas, en semanas desde que se apruebe el plan. Las fases 1 y 4 pueden avanzar en paralelo.

### Fase 0. Decisiones (semanas 1–2)

| # | Decisión | Propuesta | Quién decide |
|---|---|---|---|
| D1 | Licencia de los datos | **CC BY 4.0** | PI, dirección del CCG y jurídico de la UNAM |
| D2 | Licencia de la documentación | CC BY 4.0, para unificar (hoy es CC BY-SA) | Equipo |
| D3 | Licencia del software | Mantener MIT | Equipo de desarrollo |
| D4 | Desde cuándo rige | Desde la próxima release (indicar número y fecha), y decidir si se extiende a las anteriores | PI |
| D5 | Qué hacer con el EULA de 2006 | Retirarlo y sustituirlo por unos "Términos de uso del sitio" breves (descargo de responsabilidad, uso razonable de la API) | PI y jurídico |
| D6 | Mecanismo para RNAcentral | Opción (a), (b) o (c) de la sección 3.2 | PI y jurídico, tras consultar a RNAcentral |
| D7 | Texto de atribución estándar | Ver la propuesta al final de esta fase | Equipo |
| D8 | Idioma oficial del portal de documentación | Inglés, con el glosario traducido | Equipo |

Propuesta de texto de atribución (D7):

> "Data from RegulonDB (https://regulondb.ccg.unam.mx), release X.Y, licensed under CC BY 4.0. Please cite: [artículo vigente]."

**Entregable:** un acta de decisiones guardada en `docs/plans/`.

### Fase 1. Revisión de derechos de terceros (semanas 1–4)

1. Hacer un inventario de los campos y colecciones que provienen de fuentes externas (EcoCyc, GO, ECO, GEO/SRA, abstracts de publicaciones e imágenes). Base: fichas `07_technical_reference/collection_*` y la colección `externalCrossReferences`.
2. Consultar a SRI sobre la redistribución, bajo CC BY, de los datos importados de EcoCyc.
3. Para cada fuente, decidir si se incluye bajo CC BY, se excluye o se marca con su propia licencia.

**Entregable:** una tabla de procedencia y licencia por colección (posible página `07_technical_reference/data_provenance_licensing.md`).

### Fase 2. Redacción de los textos (semanas 3–5, en una rama `license-cc-by`)

| Archivo | Cambio propuesto |
|---|---|
| `00_about_policies/license.md` | Reescribirlo con versión 2.0 y fecha: datos CC BY 4.0, software MIT, documentación según D2, excepciones de terceros, atribución recomendada y fecha de vigencia. Eliminar §2 (uso comercial). Convertir §6 en "buenas prácticas solicitadas" |
| `00_about_policies/terms_conditions.md` | Sustituirlo según D5. Conservar el EULA 2006 solo como histórico, si se decide así |
| `00_about_policies/fair_policy.md` §5 | Apuntar a `license.md` con CC BY 4.0 (quitar CC BY-SA) |
| `00_about_policies/how_to_cite.md` | Añadir el texto de atribución CC BY y la cita vigente |
| `00_about_policies/ethics_and_download_policy.md` y `README.md` de la sección | Revisar los enlaces y la mención a la licencia |
| `00_about_policies/credits.md` | Marcar la imagen CC BY-NC-SA como excepción |
| `README.md` y `CONTRIBUTING.md` | Licencia de la documentación según D2 |
| `02_data_access/dataset_downloads.md`, `database_dumps.md` y `api_access.md` | Añadir un aviso breve de licencia y atribución en cada canal de acceso |
| `05_releases_updates/release_notes.md` | Registrar el cambio de licencia en la release en que entre en vigor |
| `docs.config.json` | Actualizar si cambia el nombre o el título de `terms_conditions` |
| Solicitud GCBR, respuesta 4d (Drive) | Reescribirla con la licencia nueva y la URL pública de `license.md` |

**Entregable:** un pull request revisado por el equipo y por jurídico.

### Fase 3. Propagación fuera del repositorio (semanas 5–7)

Lista de verificación:

- [ ] Pie y páginas del sitio web
- [ ] Página de descargas
- [ ] Cabeceras de los archivos descargables (TSV, JSON, GFF)
- [ ] Metadatos de la API GraphQL
- [ ] Imágenes Docker y dumps de MongoDB
- [ ] Registros de Zenodo de la nueva release (campo `license`)
- [ ] FAIRsharing, re3data e identifiers.org
- [ ] `LICENSE` y `README` en los repos de `github.com/regulondbunam`
- [ ] Comunicación a D3/DSMZ y a RNAcentral, con el mecanismo elegido en D6
- [ ] Anuncio a usuarios (release notes y correo o redes)

### Fase 4. Cierre de brechas de la documentación (semanas 2–10, priorizado por GCBR)

**Prioridad 1: bloquea campos de la solicitud GCBR**

1. `04_curation`: escribir `curation_workflow`, `classical_curation`, `ht_data_curation`, `evidence_classification` y `quality_control`. Responde a 3e i y a 3e ii; el placeholder "x% PALOMA" se resuelve con datos de calidad.
2. `05_releases_updates/release_notes.md` y `version_history.md`. Responde a 3e iii, versionado y QA.
3. Crear `07_technical_reference/identifier_policy.md`, sobre el formato RDBECOLI, la persistencia y la resolución. Responde a 3a.
4. Publicar la tabla de volumen de datos por entidad y release. Responde a 3b; se puede reusar `database_collections_index.md`.
5. Crear `05_releases_updates/geographic_usage.md` y `download_metrics.md` con cifras validadas, periodo y método. Responde a 2a.iii y 2a.iv.

**Prioridad 2: navegación y publicación**

6. Actualizar `SUMMARY.md` con todos los archivos que tienen contenido. Ocultar o rellenar los vacíos, para que la navegación no muestre páginas en blanco.
7. Ampliar `docs.config.json` para que publique las secciones 01 a 07.
8. Resolver los duplicados:
   - `02_data_access/technical_resources/database_collections/*` → redirigir a `07_technical_reference`
   - `standards_ontologiest.md`
   - `04_curation/glossary.md`

**Prioridad 3: contenido de usuario**

9. `03_tools_visualizations`, con los 10 archivos y capturas actualizadas.
10. `06_tutorials_videos`, con enlaces a videos y tutoriales; responde también a la nota del revisor en 3g iii.
11. `01_search_browse`: `catalog_navigation`, `collections` y `ontologies_mco`.

### Fase 5. Higiene del repositorio (semana 2, rápida)

- Añadir `.DS_Store` a `.gitignore` y sacarlo del índice de git.
- Borrar `to_delete/` y las imágenes sueltas, una vez confirmado.
- Dejar un solo PDF de Concepts, en `context/pdfs/`.
- Confirmar o descartar el cambio pendiente en `glossary.md`.
- Actualizar `docs/README.md` y `docs/06_gcbr_traceability_matrix.md`, y registrar una nueva entrada en `docs/09_document_review_history.md`.

### Fase 6. Control de calidad y cierre (semanas 10–11)

- Cruzar cada cifra de la documentación con la solicitud de Drive (tabla 3.3.E) y dejar una sola fuente por métrica.
- Comprobar todos los enlaces internos y externos.
- Buscar con `grep` que no quede ninguna mención a "BY-NC", "BY-SA" (salvo excepciones documentadas), "non-commercial" ni "EULA".
- Hacer una revisión final por el PI y, si hay cambios contractuales, por jurídico.

---

## 5. Preguntas abiertas para el equipo

1. ¿Quién en la UNAM o el CCG tiene la facultad de aprobar el cambio de licencia de una base de datos de la UNAM?
2. ¿Hay convenios vigentes (licencias comerciales o acuerdos con empresas) firmados bajo el esquema actual que deban respetarse?
3. ¿Qué subconjunto de datos se enviaría a RNAcentral y cuál a D3?
4. ¿La documentación debe quedar en CC BY 4.0, igual que los datos, o se mantiene en CC BY-SA?
5. ¿Desde qué versión rige el cambio, y aplica también a las releases anteriores?
6. ¿Cuál es la cifra validada del país sede en el tráfico (4.46 % o 7.73 %) y el periodo de medición?
7. ¿NSERC (Canadá) es un financiador real de RegulonDB? Hoy aparece solo en la respuesta 1c.

## 6. Criterios de terminado

- Una sola licencia de datos declarada en todo el repositorio, el sitio, los archivos descargables y los registros externos.
- Fuentes de terceros identificadas, cada una con su tratamiento documentado.
- Ningún archivo vacío enlazado desde `SUMMARY.md`.
- Los campos 3a, 3b, 3e i, 3e iii y 4d de la solicitud GCBR respaldados por una página pública.
- Cifras idénticas entre la documentación y la solicitud.

---

### Referencias externas consultadas

- RNAcentral, licencia CC0 desde la release 20: https://blog.rnacentral.org/2022/04/rnacentral-release-20.html
- BacDive (DSMZ), licencia CC BY 4.0: https://bacdive.dsmz.de/news
- BioCyc/EcoCyc, licencia de archivos de datos: https://metacyc.org/download.shtml
- GBC, *GCBR Concept and Selection Process* (copia local en `context/global-biodata-info/`)
- Creative Commons BY 4.0, texto legal: https://creativecommons.org/licenses/by/4.0/legalcode
