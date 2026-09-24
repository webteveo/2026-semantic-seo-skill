# seo-local-semantico-2026

Skill de Claude para arquitectura semántica, producción de contenido y GEO (visibilidad en respuestas de IA) de sitios de servicios locales en Uruguay y Argentina, más el informe de investigación 2025–2026 en el que se basa.

## Contenido del repo

- `seo-local-semantico-2026/` — la skill.
  - `SKILL.md`: principios, reglas duras etiquetadas ([RANKING] / [CONVERSIÓN] / [TRÁMITE] / [GEO]) y 5 flujos: nuevo nicho, brief y redacción de página servicio + zona (salida en HTML para plantilla PHP), escalar sin contenido escalado, auditoría semántica y E-E-A-T, checklist GEO.
  - `references/`: `investigacion-2026.md`, `location-pages.md`, `on-page-formulas.md`, `entidades-y-schema.md`, `topical-map.md`, `geo-ia.md`, `eeat-servicios.md`, `qa-checklist.md`, `zonas-rioplatenses.md`.
  - `assets/`: `plantilla-servicio-zona.html`, `brief-zona.md`, `robots.txt`.
  - `evals/evals.json`: tres casos de prueba (redactar página de zona, arquitectura de sitio nuevo, auditoría).
- `informe/INFORME-INVESTIGACION-2026.md` — informe consolidado por bloques A–H con etiquetas de evidencia, contradicciones, qué cambió 2024→2026 y diagnóstico del método.
- `informe/bloques/` — anexos completos de cada bloque de investigación (A: Google 2025–2026, B: E-E-A-T y leak, C: semántico y entidades, D: location pages, E: on-page, F: GEO, G: local, H: técnico y schema).
- `seo-local-semantico-2026.skill` — paquete instalable (botón "Save skill" en Claude).

## Convivencia con `cheloseo`

`cheloseo` prioriza (qué mueve la aguja, fase, ficha GBP, enlaces, evaluación de nicho, rank and rent). `seo-local-semantico-2026` produce (entidad, topical map, URLs, briefs, redacción, fórmulas on-page, schema, escala segura, E-E-A-T, GEO).

## Limitación de la investigación

El entorno bloqueó la apertura directa de casi todos los sitios; las citas de documentación de Google provienen de espejos textuales y de resúmenes de búsqueda. Antes de citar texto literal a un cliente, abrir la URL original. Lista de pendientes al final del informe.
