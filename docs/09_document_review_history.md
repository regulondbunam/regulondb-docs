# Historial de Revision de Documentos para Cumplimiento GCBR

## Objetivo
Registrar, por documento del portal, que estaba bien, que faltaba para cumplir como evidencia publica, y que accion se definio.

## Criterios usados
- `Cumple`: ya funcionaba como evidencia publica.
- `Parcial`: tenia base util, pero faltaba estructura o trazabilidad.
- `No cubre`: no existia seccion dedicada para el requisito.

## Revision 2026-02-10

| Documento | Requisito relacionado | Lo que tenia bien | Lo que faltaba | Estado inicial | Accion definida | Estado actual |
|---|---|---|---|---|---|---|
| `00_about_policies/about_us.md` | 1a, 1b | Define claramente que RegulonDB es knowledge base, mision, alcance cientifico y contenido | Faltaba version explicita reutilizable para evidencia GCBR en formato corto | Parcial | Reusar como base y complementar con paginas especificas | En progreso |
| `00_about_policies/credits.md` | 1d, 4b | Contiene liderazgo, equipos, SAB, funciones y actividades | Faltaba formato formal de gobernanza (responsabilidades, vigencia, mecanismo de actualizacion, COI) | Parcial | Crear documento formal de gobernanza y dejar credits como reconocimiento | Complementado por nuevo documento |
| `00_about_policies/funding_credits.md` | 4a | Lista fuentes de financiamiento nacionales e internacionales | Faltaba estructura temporal y trazabilidad por periodos/objetivos | Parcial | Mantener y luego normalizar formato de evidencia publica | Actualizado |
| `00_about_policies/privacy_policy.md` | 4e | Politica publica de privacidad y uso de analytics | Faltaba metadato de revision visible y posible responsable explicito | Parcial | Ajuste editorial posterior con fecha/responsable | Actualizado |
| `00_about_policies/cookie_policy.md` | 4e | Politica publica de cookies y control por navegador | Tenia placeholder en fecha de actualizacion | Parcial | Reemplazar placeholder y agregar responsable | Actualizado |
| `00_about_policies/ethics_and_download_policy.md` | 4f, 2a | Cubre etica, FAIR y uso de analytics | Tenia placeholders y enlaces por cerrar | Parcial | Completar placeholders y validar enlaces | Actualizado |
| `00_about_policies/fair_policy.md` | 4d, 3d | Declara implementacion FAIR, acceso y estandares | Faltaba revisar enlaces internos y consistencia de rutas | Parcial | Correccion de enlaces y versionado de politica | Actualizado |
| `00_about_policies/how_to_cite.md` | 2c | Contiene lista amplia de publicaciones y guia de citacion | Faltaba alinear enlace de historial de versiones al portal docs y metadatos de revision | Parcial | Corregir enlaces internos y agregar metadatos | Actualizado |
| `07_technical_reference/standards_ontologies.md` | 3d, 3a | Describe ontologias, evidencia e interoperabilidad | Nombre de archivo mejorable y validacion de referencias externas | Parcial | Refinar nomenclatura y actualizar referencias | Actualizado |
| `07_technical_reference/db_relationships.md` | 2d | Documenta conexiones con recursos externos y evidencia | Faltaba estructura mas trazable por recurso/relacion | Parcial | Convertir parte del contenido a tabla mantenible | Pendiente |
| `README.md` | 3e | Estructura general de documentacion y objetivos | No cubre por si solo evidencia de indicadores GCBR | Parcial | Mantener como portada, sin sobrecargar indicadores | Vigente |
| `SUMMARY.md` | 3e | Navegacion central del portal de docs | Faltaban enlaces a nuevos entregables GCBR | Parcial | Agregar enlaces a documentos nuevos | Actualizado |
| `05_releases_updates/README.md` | 3e | Era archivo vacio | Faltaba indice y proposito de seccion | No cubre | Crear indice de seccion y enlaces clave | Actualizado |
| `07_technical_reference/README.md` | 3e | No existia como indice de seccion | Faltaba navegacion publica para referencia tecnica | No cubre | Crear indice y proposito de seccion | Creado |
| `07_technical_reference/database_schema_overview.md` | 3b | No existia antes | Faltaba vision estructural publica de la base de datos | No cubre | Crear overview tecnico del esquema y convenciones de IDs | Creado |
| `07_technical_reference/database_collections_index.md` | 3b | No existia antes | Faltaba indice de colecciones con volumen y rol | No cubre | Crear indice de colecciones documentadas | Creado |
| `07_technical_reference/collection_genes.md` | 3b | No existia antes | Faltaba ficha tecnica de coleccion genes | No cubre | Crear documentacion de campos y relaciones | Creado |
| `07_technical_reference/collection_regulators.md` | 3b | No existia antes | Faltaba ficha tecnica de coleccion regulators | No cubre | Crear documentacion de campos y relaciones | Creado |
| `07_technical_reference/collection_regulatory_interactions.md` | 3b | No existia antes | Faltaba ficha tecnica de coleccion regulatoryInteractions | No cubre | Crear documentacion de campos y relaciones | Creado |
| `07_technical_reference/collection_operons.md` | 3b | No existia antes | Faltaba ficha tecnica de coleccion operons | No cubre | Crear documentacion de campos y relaciones | Creado |
| `07_technical_reference/collection_promoters.md` | 3b | No existia antes | Faltaba ficha tecnica de coleccion promoters | No cubre | Crear documentacion de campos y relaciones | Creado |
| `07_technical_reference/collection_transcription_units.md` | 3b | No existia antes | Faltaba ficha tecnica de coleccion transcriptionUnits | No cubre | Crear documentacion de campos y relaciones | Creado |
| `07_technical_reference/collection_evidences.md` | 3b | No existia antes | Faltaba ficha tecnica de coleccion evidences | No cubre | Crear documentacion de campos y relaciones | Creado |
| `07_technical_reference/collection_*.md (resto de colecciones)` | 3b | No existia documentacion completa por coleccion | Faltaban fichas para colecciones de soporte y metadatos | No cubre | Crear fichas tecnicas restantes con diccionario de datos | Creado |
| `02_data_access/dataset_downloads.md` | 3f | Era archivo vacio | Faltaba guia publica de datasets descargables | No cubre | Crear guia de acceso y descarga | Actualizado |
| `02_data_access/api_access.md` | 3f | Era archivo vacio | Faltaba guia publica de acceso programatico | No cubre | Crear guia API/GraphQL basada en portal | Actualizado |
| `02_data_access/database_dumps.md` | 3f | Era archivo vacio | Faltaba guia publica de dumps/exportaciones | No cubre | Crear guia de dumps con enlaces oficiales | Actualizado |
| `02_data_access/technical_resources/README.md` | 3e | Era archivo vacio | Faltaba indice de recursos tecnicos | No cubre | Crear indice y alcance tecnico de seccion | Actualizado |
| `02_data_access/technical_resources/web_services_usage.md` | 3f | Era archivo vacio | Faltaba guia operativa de web services | No cubre | Crear guia publica de uso de servicios | Actualizado |
| `02_data_access/technical_resources/docker_installation.md` | 3f | Era archivo vacio | Faltaba guia de despliegue local con Docker | No cubre | Crear guia publica de instalacion/uso Docker (comandos, endpoints y actualizacion de releases) | Actualizado |
| `02_data_access/technical_resources/mongodb_installation.md` | 3f | Era archivo vacio | Faltaba guia de uso local con MongoDB | No cubre | Crear guia publica de instalacion/flujo local | Actualizado |
| `00_about_policies/README.md` | 3e | Indice de politicas y contexto | Faltaban enlaces a nuevos entregables GCBR | Parcial | Agregar enlaces de navegacion | Actualizado |
| `00_about_policies/global_dimension.md` | 1c | No existia antes | Se requeria pagina dedicada de dimension global | No cubre | Crear pagina publica de dimension global | Creado |
| `00_about_policies/staff_effort_fte.md` | 1d | No existia antes | Se requeria tabla FTE agregada y metodologia publica | No cubre | Crear pagina publica resumida de FTE | Creado |
| `00_about_policies/governance_advisory.md` | 4b | No existia antes | Se requeria estructura formal de gobernanza publica | No cubre | Crear pagina publica de gobernanza y SAB | Creado |
| `00_about_policies/data_preservation_policy.md` | 4c | No existia antes | Se requeria politica publica explicita de preservacion y continuidad | No cubre | Crear politica publica de preservacion y continuidad | Creado |
| `05_releases_updates/usage_metrics.md` | 2a.i | No existia antes | Se requeria evidencia publica agregada de uso web | No cubre | Crear pagina publica con metricas agregadas y metodologia GA4 | Creado |
| `05_releases_updates/research_usage.md` | 2b | No existia antes | Se requeria evidencia publica de uso en investigacion | No cubre | Crear pagina publica con indicadores agregados y metodologia | Creado |
| `07_technical_reference/technical_performance.md` | 3c | No existia antes | Se requeria evidencia publica de desempeno tecnico | No cubre | Crear pagina publica de desempeno tecnico en nivel agregado | Creado |
| `05_releases_updates/impact_stories.md` | 5a | No existia antes | Se requeria evidencia narrativa publica de impacto | No cubre | Crear pagina publica de historias de impacto verificables | Creado |
| `05_releases_updates/counterfactual.md` | 5b | No existia antes | Se requeria narrativa publica de escenario sin el recurso | No cubre | Crear pagina publica de counterfactual | Creado |
| `01_search_browse/Copia de search_overview.md` | 3e | Era duplicado del archivo principal | Generaba redundancia y riesgo de divergencia | No cubre | Mover a `to_delete/` y conservar solo archivo canonico | Actualizado |

## Notas de uso
- Este historial documenta evaluacion para evidencia publica del portal, no el llenado de la solicitud GCBR.
- Cada nueva iteracion debe anadir fecha y actualizar `Estado actual`.
