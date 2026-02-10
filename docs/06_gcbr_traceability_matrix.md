# Matriz de Trazabilidad GCBR para Documentacion Publica del Portal

## Objetivo
Traducir los requisitos del documento `GCBRS-Application.docx` en acciones concretas de documentacion publica complementaria para el portal de RegulonDB (`https://regulondb.ccg.unam.mx/`).

## Alcance de este proyecto
- `En alcance`: paginas y secciones publicas del portal que evidencien cumplimiento (politicas, metadatos, guias, trazabilidad, indicadores publicables).
- `Fuera de alcance`: llenado del formulario de solicitud GCBR o gestion administrativa de la aplicacion.
- `Nota`: cuando se requieran metricas internas para construir evidencia publica, este proyecto solo define como documentarlas y publicarlas.

## Criterios de estado
- `Completo`: existe contenido explicito y utilizable.
- `Parcial`: existe contenido relacionado, pero falta estructura/evidencia GCBR.
- `Faltante`: no hay seccion o evidencia documental identificada.

## Matriz
| Requisito GCBR | Estado | Evidencia publica actual (archivo) | Brecha en portal | Accion recomendada para el portal | Prioridad |
|---|---|---|---|---|---|
| 1a. Deposition database and/or Knowledge base | Completo | `00_about_policies/about_us.md` | No se presenta en formato de respuesta GCBR | Agregar seccion corta "Tipo de recurso (GCBR)" con SI/NO y justificacion | Media |
| 1b. Scope statement | Completo | `00_about_policies/about_us.md` | Falta version resumida orientada a lectura publica y evidencia | Crear bloque "Scope statement" publico reutilizable | Media |
| 1c. Global dimension | Parcial | `00_about_policies/about_us.md`, `00_about_policies/funding_credits.md` | No esta consolidado en una narrativa unica con evidencia | Crear pagina dedicada de dimension global y colaboraciones internacionales | Alta |
| 1d. Staff effort (FTE por anio) | Parcial | `00_about_policies/credits.md` | No hay tabla FTE anual publica y versionada | Agregar tabla FTE 2020-presente con criterio de calculo | Alta |
| 2a.i. Usage via web analytics | Parcial | `00_about_policies/privacy_policy.md`, `00_about_policies/ethics_and_download_policy.md` | Falta serie anual/mensual consolidada y metodologia | Crear pagina de metricas de uso con tabla por anio y fuente (GA) | Alta |
| 2a.ii. Usage via log analytics | Faltante | N/A | No hay seccion publica de metodologia alterna por logs | Definir si aplica en el portal o publicar "No aplica" con justificacion | Media |
| 2a.iii. Geographic distribution of users | Faltante | N/A | No hay resumen geografico publicable en docs | Agregar seccion con % host vs internacional y top paises | Alta |
| 2a.iv. Data downloads | Parcial | `02_data_access/dataset_downloads.md` | Hay guia operativa pero no metricas de descarga | Agregar metricas mensuales/anuales de requests/downloads | Alta |
| 2b. Usage in research (citations) | Parcial | `00_about_policies/about_us.md`, `00_about_policies/how_to_cite.md` | No hay indicador anual de citacion/impacto | Agregar tablero de impacto bibliometrico anual | Alta |
| 2c. Citation of key publications | Completo | `00_about_policies/how_to_cite.md` | Falta formato de "publicaciones clave del recurso" en pagina dedicada | Estandarizar lista con DOI, tipo de aporte y version asociada | Media |
| 2d. Connections to other data resources | Completo | `07_technical_reference/db_relationships.md` | Requiere evidencia mas trazable y mantenible | Convertir ejemplos en tabla de interoperabilidad por recurso externo | Media |
| 3a. Identifier use | Parcial | `01_search_browse/gene_search.md`, `01_search_browse/operon_search.md`, `07_technical_reference/standards_ontologies.md` | Falta politica unica de identificadores persistentes | Crear referencia tecnica de IDs, persistencia y resolucion | Alta |
| 3b. Data volume | Faltante | N/A | No hay tabla de volumen de datos por periodo | Publicar inventario de volumen por tipo de entidad y version | Alta |
| 3c. Technical performance | Faltante | N/A | No hay disponibilidad, SLA ni tiempos de respuesta documentados | Crear pagina de rendimiento y confiabilidad operativa | Alta |
| 3d. Use of standards | Completo | `07_technical_reference/standards_ontologies.md` | Archivo con nombre/titulo mejorable y enlaces a validar | Renombrar y actualizar referencias a estandares vigentes | Media |
| 3e. Documentation | Completo | `README.md`, `SUMMARY.md`, secciones `01`-`07` | Cobertura desigual en calidad, vigencia y formato publicable | Aplicar plantilla comun con fecha de revision y responsable | Alta |
| 3f. Data availability | Completo | `02_data_access/README.md`, `02_data_access/api_access.md`, `02_data_access/database_dumps.md` | Falta declaracion de continuidad de servicio | Agregar nota de disponibilidad, ventanas de mantenimiento y fallback | Media |
| 3g. User support | Completo | `00_about_policies/helpdesk-protocol.md`, `00_about_policies/contact_us.md` | Falta KPI de soporte (tiempo de respuesta) | Incorporar SLA de atencion y canales oficiales | Media |
| 4a. Funding | Completo | `00_about_policies/funding_credits.md` | Puede faltar trazabilidad temporal por convocatoria | Agregar periodos, fuente, objetivo y vigencia por financiamiento | Media |
| 4b. Scientific Advisory Board | Parcial | `00_about_policies/credits.md` | Falta estructura formal de gobernanza | Crear pagina de gobernanza y comite asesor con roles | Alta |
| 4c. Data preservation | Faltante | N/A | No hay politica publica explicita de preservacion/backup/archivo | Crear politica de preservacion y continuidad a largo plazo | Alta |
| 4d. Open Science | Completo | `00_about_policies/fair_policy.md`, `00_about_policies/license.md`, `00_about_policies/ethics_and_download_policy.md` | Hay enlaces internos desactualizables | Validar y corregir enlaces, incluir versionado de politica | Media |
| 4e. Privacy policy | Completo | `00_about_policies/privacy_policy.md`, `00_about_policies/cookie_policy.md` | Requiere control de vigencia visible | Agregar fecha de ultima revision y responsable legal | Media |
| 4f. Ethics policy | Completo | `00_about_policies/ethics_and_download_policy.md` | Hay placeholders (URL de citacion) | Reemplazar placeholders y completar referencias | Alta |
| 5a. Impact stories | Faltante | N/A | No existe seccion narrativa de casos de impacto | Crear `05_releases_updates/impact_stories.md` con casos verificables | Alta |
| 5b. Counterfactual | Faltante | N/A | No existe narrativa "que pasaria sin el recurso" | Crear `05_releases_updates/counterfactual.md` con evidencia | Alta |

## Acciones transversales recomendadas
1. Definir plantilla unica por pagina: resumen, alcance, evidencia, responsable, fecha de revision.
2. Estandarizar indicadores cuantitativos (uso, descargas, citacion, soporte) con periodicidad fija.
3. Crear anexo de gobernanza y preservacion para cerrar brechas de infraestructura GCBR.
4. Vincular cada indicador GCBR con al menos una evidencia documental mantenible.
5. Marcar en cada pagina si la evidencia es publica (portal) o depende de dato interno no publicado.

## Notas de implementacion
- Esta matriz es una base de trabajo para documentacion publica del portal y no sustituye la validacion institucional de cifras.
- Toda metrica publicada debe incluir fuente, periodo y metodologia.
- Si un indicador requiere datos internos no publicables, se debe publicar al menos la metodologia y nivel de agregacion permitido.
