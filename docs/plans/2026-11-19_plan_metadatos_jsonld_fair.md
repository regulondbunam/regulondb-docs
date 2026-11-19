# Plan: metadatos estructurados (JSON-LD) para mejorar la evaluación FAIR

**Fecha:** 2026-11-19
**Estado:** decisiones resueltas; listo para iniciar la parte 1
**Responsables:** Equipo de documentación

El plan se divide en dos partes. **La parte 1 es la prioridad actual**: que el proyecto de documentación (`https://github.com/regulondbunam/regulondb-docs`) sea reconocido por los evaluadores FAIR. La parte 2, los metadatos en la aplicación web de RegulonDB, queda para después.

## 1. Contexto

RegulonDB obtuvo una calificación baja en la evaluación FAIR porque no publica metadatos estructurados legibles por máquina. La recomendación recibida es describir la documentación como `CreativeWork` (schema.org) en un bloque `<script type="application/ld+json">`, vinculado al catálogo de datos de RegulonDB.

### Cómo evalúan los verificadores

- **FAIR-Checker** (IFB / ELIXIR-FR) recibe la URL de una página web o un DOI (el DOI se resuelve a su página) y extrae los metadatos incrustados en el HTML: JSON-LD, RDFa o microdatos. Con ellos evalúa los indicadores FAIR.
- **F-UJI** también recoge metadatos por negociación de contenido, metadatos incrustados y enlaces tipados (*signposting*); su extensión para software revisa además archivos del repositorio como `CITATION.cff` y `codemeta.json`, y la presencia de DOI.

### Diagnóstico del repositorio (2026-11-19)

| Hallazgo | Consecuencia |
|---|---|
| La página `github.com/regulondbunam/regulondb-docs` la genera GitHub; no se puede agregar JSON-LD en su HTML. | Evaluada directamente, la URL de GitHub nunca tendrá los metadatos `CreativeWork`. Se necesita una página propia o un DOI. |
| No hay archivo `LICENSE`. La licencia CC BY-NC 4.0 solo aparece en el texto de `README.md` y `CONTRIBUTING.md`. | Ni GitHub ni los evaluadores detectan la licencia de forma automática. |
| No hay `CITATION.cff`, `.zenodo.json` ni `codemeta.json`. | No hay metadatos de cita ni de autoría legibles por máquina; GitHub no muestra el botón "Cite this repository". |
| No hay DOI ni versiones etiquetadas (*tags*) del repositorio. | No hay identificador persistente; los indicadores F1 (identificador) y A1 (acceso por identificador) fallan. |
| El repositorio incluye material interno: `context/` (copia de datos MongoDB, PDFs y documentos GCBR), `docs/` (planes), `to_delete/` y `style_sheet/`. | Ese material no debe publicarse en la página ni en los archivos depositados en Zenodo. |

### Línea base: evaluación FAIR del sitio

Evaluación de `https://regulondb.ccg.unam.mx/` con los indicadores de FAIR-Checker (0 a 2 puntos cada uno; total sobre 24):

| F1A | F1B | F2A | F2B | A1.1 | A1.2 | I1 | I2 | I3 | R1.1 | R1.2 | R1.3 | Total | % |
|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| 2 | 0 | 0 | 0 | 2 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 4/24 | 16.7 |

Solo se cumplen el identificador único (la URL, F1A) y el protocolo abierto (HTTPS, A1.1). Todos los indicadores que dependen de metadatos legibles por máquina están en cero. La misma puntuación la obtienen la mayoría de los recursos de la UNAM evaluados en la misma tabla.

| Indicador | Qué evalúa | Acción de este plan |
|---|---|---|
| F1B | Identificador persistente | DOI de Zenodo (sección 3.3). |
| F2A, F2B | Metadatos estructurados con vocabulario compartido | Bloque JSON-LD schema.org (secciones 3.2 y 4). |
| I1, I2, I3 | Representación formal (RDF), vocabularios FAIR y enlaces calificados a otros recursos | JSON-LD con `@id`, schema.org y enlaces a RegulonDB, al repositorio y al DOI. |
| R1.1 | Licencia en los metadatos | `license` en el JSON-LD, `LICENSE`, `CITATION.cff` y `.zenodo.json`. |
| R1.2 | Procedencia (autor, editor, fechas) | `author`, `publisher`, `dateModified` y `version`. |
| R1.3 | Estándares de la comunidad | schema.org; revisar el perfil de Bioschemas aplicable. |
| A1.2 | Autenticación y autorización | No aplica a contenido abierto; no se espera cambio. |

La primera tarea del plan es registrar también la línea base del repositorio (`https://github.com/regulondbunam/regulondb-docs`), que se evaluará por separado.

# Parte 1. Repositorio de documentación (prioridad actual)

## 2. Objetivo

Que el proyecto de documentación tenga:

1. Una **página de inicio propia** (GitHub Pages) con el bloque JSON-LD `CreativeWork`, que FAIR-Checker y F-UJI puedan leer.
2. Un **identificador persistente** (DOI de Zenodo) que resuelva a una página con metadatos.
3. **Archivos de metadatos estándar** en el repositorio: licencia, cita y metadatos de depósito.

## 3. Componentes

### 3.1 Archivos de metadatos en la raíz del repositorio

| Archivo | Contenido | Para qué sirve |
|---|---|---|
| `LICENSE` | Texto legal de CC BY-NC 4.0 (`https://creativecommons.org/licenses/by-nc/4.0/legalcode.txt`). | Licencia detectable por máquina. GitHub no tiene CC BY-NC en su lista de licencias reconocidas y la mostrará como "Other"; los evaluadores leen la licencia de los metadatos JSON-LD y de Zenodo. |
| `CITATION.cff` | Título, autor (RegulonDB Team, entidad colectiva), versión, fecha, DOI, licencia (`CC-BY-NC-4.0`), URL del repositorio y referencia preferida (Salgado *et al.*, 2024). | GitHub muestra "Cite this repository"; F-UJI y Zenodo lo leen. |
| `.zenodo.json` | Metadatos del depósito: título, autores, descripción, licencia `cc-by-nc-4.0`, tipo de depósito, palabras clave, relación con RegulonDB (`documents`, hacia `https://regulondb.ccg.unam.mx/`). | Zenodo los usa al crear cada versión, en lugar de los valores por omisión. |
| `_includes/regulondb_documentation.jsonld` | Bloque `CreativeWork` (sección 4), con `version`, `dateModified` y DOI tomados de `_config.yml`. | Fuente única del JSON-LD: la plantilla lo inserta en cada página y también se publica como archivo en `assets/metadata/regulondb_documentation.jsonld` (enlazado con `rel="describedby"`). |
| `.gitattributes` | `context/ export-ignore`, `docs/ export-ignore`, `to_delete/ export-ignore`, `style_sheet/ export-ignore`. | Excluye el material interno del archivo `.zip` de cada versión, que es lo que Zenodo deposita. |

### 3.2 Página de inicio con GitHub Pages

1. Activar GitHub Pages para la rama `main` (URL prevista: `https://regulondbunam.github.io/regulondb-docs/`).
2. Agregar una configuración mínima de Jekyll:
   - `_config.yml`: título, descripción, URL base, plugin `jekyll-relative-links` (para que los enlaces `.md` funcionen) y `exclude:` con `context/`, `docs/`, `to_delete/`, `style_sheet/`, `03_tools_visualizations/` y `06_tutorials_videos/`.
   - `_layouts/default.html`: plantilla que inserta en `<head>` el contenido de `assets/metadata/regulondb_documentation.jsonld` y la hoja de estilos `assets/css/regulondb-docs.css`, y aplica las reglas de la guía de estilo (encabezado con icono y sección, recuadro "Related Content").
   - `_includes/`: el bloque JSON-LD y, si se necesita, el encabezado.
3. La portada es el `README.md` de la raíz. Como el bloque está en la plantilla, aparece en todas las páginas, en el HTML estático, sin depender de JavaScript.
4. Agregar `<link rel="license">` y `<link rel="cite-as">` (con el DOI) en `<head>`: son los enlaces de *signposting* más sencillos.

GitHub Pages solo publica; la aplicación web de RegulonDB sigue leyendo los markdown desde `docs.config.json` como hasta ahora.

### 3.3 DOI con Zenodo

1. Conectar el repositorio con Zenodo (integración GitHub–Zenodo) desde la cuenta institucional de RegulonDB.
2. Crear la primera versión (*release*) en GitHub, `v14.5.1` (decisión D2), con un enlace a la nota de la release en `https://regulondb.ccg.unam.mx/releasesNote`. Zenodo deposita el `.zip` de la versión y asigna dos DOI: uno de la versión y un **DOI conceptual** que siempre apunta a la versión más reciente.
3. Usar el DOI conceptual en `CITATION.cff`, en el JSON-LD (`identifier`), en el README (insignia) y en `how_to_cite.md`.
4. Revisar el registro en Zenodo: licencia, autores, tipo y la relación con RegulonDB deben coincidir con `.zenodo.json`.

### 3.4 Cambios en el README y en la cita

- Insignias de DOI y de licencia al inicio del `README.md`.
- Sección "How to Cite This Documentation" con el DOI, además de la cita de RegulonDB.
- Enlace a la página de GitHub Pages.
- Actualizar `00_about_policies/how_to_cite.md` con la cita de la documentación.

## 4. Bloque JSON-LD de la documentación (`CreativeWork`)

Contenido propuesto para `assets/metadata/regulondb_documentation.jsonld`; los valores entre `< >` se completan cuando exista el DOI.

```json
{
  "@context": "https://schema.org",
  "@type": "CreativeWork",
  "@id": "https://regulondbunam.github.io/regulondb-docs/#documentation",
  "name": "RegulonDB Documentation",
  "description": "Documentation of RegulonDB: policies, search and browse, data access, glossary, evidence classification, releases, and technical reference.",
  "url": "https://regulondbunam.github.io/regulondb-docs/",
  "identifier": "https://doi.org/10.5281/zenodo.<DOI de la documentación>",
  "isBasedOn": "https://github.com/regulondbunam/regulondb-docs",
  "version": "14.5.1",
  "inLanguage": "en",
  "license": "https://creativecommons.org/licenses/by-nc/4.0/",
  "dateModified": "2026-11-19",
  "publisher": {
    "@type": "Organization",
    "name": "Centro de Ciencias Genómicas, Universidad Nacional Autónoma de México",
    "url": "https://www.ccg.unam.mx/"
  },
  "author": {
    "@type": "Organization",
    "name": "RegulonDB Team",
    "url": "https://regulondbunam.github.io/regulondb-docs/00_about_policies/credits.html",
    "email": "regulondb@ccg.unam.mx"
  },
  "maintainer": {
    "@type": "Organization",
    "name": "RegulonDB Team",
    "email": "regulondb@ccg.unam.mx"
  },
  "about": {
    "@type": "DataCatalog",
    "@id": "https://regulondb.ccg.unam.mx/#catalog",
    "name": "RegulonDB",
    "url": "https://regulondb.ccg.unam.mx/"
  }
}
```

Notas:

- `version` sigue la numeración de los releases de RegulonDB (D2); `version` y `dateModified` se actualizan con cada versión de la documentación.
- `author.url` apunta a la página de créditos publicada en GitHub Pages.
- Cuando la aplicación web publique su propio bloque `DataCatalog` (parte 2), `about` puede reducirse a `{"@id": "https://regulondb.ccg.unam.mx/#catalog"}`.

## 5. Decisiones

| # | Decisión | Resolución (2026-11-19) |
|---|---|---|
| D1 | Autores en `CITATION.cff`, `.zenodo.json` y JSON-LD | **RegulonDB Team** como autor colectivo, con enlace a la página de créditos (`00_about_policies/credits.md`), donde se reconoce a las personas. |
| D2 | Esquema de versiones de la documentación | **La numeración de los releases de RegulonDB**, con sus notas en `https://regulondb.ccg.unam.mx/releasesNote`. La documentación de la release 14.5.1 se publica como `v14.5.1`; si la documentación cambia entre dos releases de datos, se agrega un sufijo (`v14.5.1-r1`, `v14.5.1-r2`…). |
| D3 | Tipo de depósito en Zenodo | **Publicación técnica** (`publication` / `technicalnote`), en lugar de `software`, que es el valor por omisión de la integración con GitHub. |
| D4 | Qué hacer con `context/` | **No forma parte de la documentación**: fue material de contexto para preparar los documentos. Queda fuera de la página y del `.zip` depositado (`exclude` y `export-ignore`). |
| D5 | Activar GitHub Pages en la organización `regulondbunam` | **Resuelta**: hay permisos de administración; se activa desde Settings → Pages del repositorio. |
## 6. Validación

| Paso | Herramienta | Criterio de aceptación |
|---|---|---|
| Línea base | FAIR-Checker y F-UJI sobre `https://github.com/regulondbunam/regulondb-docs` | Registrar la puntuación actual antes de cualquier cambio. |
| Sintaxis | Schema.org Validator (`https://validator.schema.org/`) sobre la página de GitHub Pages | El bloque `CreativeWork` se reconoce sin errores. |
| HTML estático | `curl -s https://regulondbunam.github.io/regulondb-docs/ \| grep ld+json` | El bloque aparece sin ejecutar JavaScript. |
| Cita | GitHub muestra "Cite this repository"; `cffconvert --validate` | `CITATION.cff` válido. |
| Evaluación final | FAIR-Checker sobre la página de GitHub Pages y sobre el DOI; F-UJI sobre el DOI | Mejora respecto a la línea base en identificador, metadatos, licencia y acceso. |

Guardar los reportes con fecha en `docs/fair_assessment/`.

## 7. Tareas y calendario

| # | Tarea | Depende de | Semana |
|---|---|---|---|
| 1 | Registrar la línea base en FAIR-Checker y F-UJI | — | 1 |
| 2 | Permisos para GitHub Pages (D5): confirmados | — | 1 |
| 3 | Agregar `LICENSE`, `CITATION.cff`, `.zenodo.json`, `.gitattributes` y el JSON-LD (**hecho 2026-11-19**) | 2 | 1 |
| 4 | Configurar Jekyll (`_config.yml`, `_layouts/default.html`: **hecho 2026-11-19**) y activar GitHub Pages | 3 | 2 |
| 5 | Conectar Zenodo y publicar la versión `v14.5.1` | 3 | 2 |
| 6 | Completar el DOI en `CITATION.cff`, JSON-LD, README y `how_to_cite.md`; publicar `v14.5.1-r1` | 5 | 2 |
| 7 | Validar (sección 6) y comparar con la línea base | 4, 6 | 3 |
| 8 | Agregar al proceso de cada release de RegulonDB: publicar la versión de la documentación con el mismo número y actualizar `version` y `dateModified` | 7 | 3 |

## 8. Riesgos

| Riesgo | Mitigación |
|---|---|
| Se publica material interno (`context/`, `docs/`). | `exclude` en `_config.yml` y `export-ignore` en `.gitattributes`; revisar el `.zip` antes de conectar Zenodo. |
| Enlaces rotos en GitHub Pages por rutas `.md`. | Plugin `jekyll-relative-links`; revisar los enlaces después de publicar. |
| El JSON-LD queda desactualizado. | Fuente única en `assets/metadata/` y paso del proceso de versión (tarea 8). |
| Agregar el JSON-LD solo en el `README.md`. | No cuenta como metadatos: GitHub muestra el bloque como texto, no lo incrusta en el HTML. Debe ir en la plantilla de GitHub Pages. |

# Parte 2. Aplicación web de RegulonDB (posterior)

Se retomará después de la parte 1. Puntos ya identificados el 2026-11-19:

- Las páginas del manual en el sitio (`https://regulondb.ccg.unam.mx/manual/...`) no tienen bloques `application/ld+json`.
- El sitio es una aplicación de una sola página: el HTML inicial es un contenedor vacío que depende de JavaScript, así que los metadatos deben ir en el `index.html` que entrega el servidor.
- Todas las rutas comparten el mismo `<head>`, con el título "RegulonDB Browser" y `<link rel="canonical" href="http://regulondb.ccg.unam.mx/">` (misma URL canónica para todas las páginas y con `http`).

Propuesta para entonces:

1. Publicar en la página principal un bloque `DataCatalog` + `Dataset` (release vigente), con el borrador siguiente, y en la portada del manual el mismo `CreativeWork` de la parte 1, con `sameAs` hacia la página de GitHub Pages y el DOI.
2. Corregir la URL canónica (`https`, una por ruta).
3. Agregar encabezados de *signposting* en el servidor.
4. Validar con los mismos pasos de la sección 6.

Borrador del bloque del catálogo:

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "DataCatalog",
      "@id": "https://regulondb.ccg.unam.mx/#catalog",
      "name": "RegulonDB",
      "description": "RegulonDB is the primary database on transcriptional regulation in Escherichia coli K-12, with manually curated knowledge from the literature and high-throughput datasets.",
      "url": "https://regulondb.ccg.unam.mx/",
      "license": "https://creativecommons.org/licenses/by-nc/4.0/",
      "keywords": ["transcriptional regulation", "Escherichia coli K-12", "gene regulatory network", "regulon", "promoter", "transcription factor"],
      "publisher": {
        "@type": "Organization",
        "name": "Centro de Ciencias Genómicas, Universidad Nacional Autónoma de México",
        "url": "https://www.ccg.unam.mx/"
      },
      "citation": "https://doi.org/10.1093/nar/gkad1072",
      "subjectOf": { "@id": "https://regulondb.ccg.unam.mx/manual/#documentation" },
      "dataset": { "@id": "https://regulondb.ccg.unam.mx/#release" }
    },
    {
      "@type": "Dataset",
      "@id": "https://regulondb.ccg.unam.mx/#release",
      "name": "RegulonDB release 14.5.1",
      "description": "Curated transcriptional regulation of Escherichia coli K-12: genes, transcription units, promoters, terminators, regulatory interactions, and regulons.",
      "version": "14.5.1",
      "datePublished": "2026-11-11",
      "license": "https://creativecommons.org/licenses/by-nc/4.0/",
      "includedInDataCatalog": { "@id": "https://regulondb.ccg.unam.mx/#catalog" },
      "citation": "https://doi.org/10.1093/nar/gkad1072",
      "distribution": [
        {
          "@type": "DataDownload",
          "name": "Downloadable datasets",
          "contentUrl": "https://regulondb.ccg.unam.mx/datasets",
          "encodingFormat": "text/tab-separated-values"
        },
        {
          "@type": "DataDownload",
          "name": "Database dump (MongoDB)",
          "contentUrl": "https://regulondb.ccg.unam.mx/download/",
          "encodingFormat": "application/bson"
        }
      ]
    }
  ]
}
```

## 9. Relación con otros planes

- [Plan de licencia y brechas de la documentación](2026-11-18_plan_licencia_cc-by_y_brechas_docs.md): la licencia CC BY-NC 4.0 (sección 0) es la que declaran estos metadatos; el registro en FAIRsharing y re3data complementa este plan.
