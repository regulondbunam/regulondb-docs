# to_delete - 2026-11-18

Archivos movidos durante la revisión de `02_data_access` para no perder trazabilidad antes de eliminarlos definitivamente.

## Movidos

- `02_data_access/technical_resources/database_collections/*.md` (7 archivos vacíos: README, examples_queries, genes, operons, promoters, regulators, regulatory_interactions)
  - Motivo: archivos vacíos que duplicaban las fichas de `07_technical_reference/collection_*.md`. "Database Collections Structure" ahora apunta a `07_technical_reference/database_collections_index.md`.
- `02_data_access/technical_resources/web_services_usage.md`
  - Motivo: duplicaba `02_data_access/api_access.md`; su contenido se fusionó en esa guía.

- `07_technical_reference/standards_ontologiest.md`
  - Motivo: versión anterior (con errata en el nombre) de `07_technical_reference/standards_ontologies.md`. Su contenido útil (referencia de Lara et al. 2024, enlace al documento de clasificación de evidencias y ejemplo de GEO) se integró en el archivo vigente.

- `02_data_access/technical_resources/docker_installation.md`
  - Motivo: duplicaba `07_technical_reference/rdb_docker_instance.md`, que es la guía que publica el portal (API & software > Docker). Las mejoras se pasaron a esa guía y los enlaces se actualizaron.

- `00_about_policies/terms_conditions.md`
  - Motivo: EULA académico de 2006 (prohibía redistribuir, modificar e integrar los datos, con vigencia de un año), incompatible con la licencia CC BY-NC 4.0 adoptada el 2026-11-18. Los términos de uso vigentes están en `00_about_policies/license.md`.

- `04_curation/glossary.md`
  - Motivo: archivo vacío; el glosario está en `04_curation/glossary/glossary.md` (inglés). La versión anterior en español se conserva como `04_curation/glossary/glossary_es.md`.

## Nota

Esta carpeta es temporal. El borrado final se realiza cuando el equipo confirme que no se requiere recuperar ningún archivo.
