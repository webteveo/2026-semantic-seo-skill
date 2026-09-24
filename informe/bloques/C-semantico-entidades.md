# BLOQUE C — SEO semántico y SEO de entidades (para sitios de servicios locales UY/AR, 50–500 páginas)

Fecha de investigación: 24 de septiembre de 2026.
Destinatario: Benja (Montevideo), consultor que arma sitios "servicio × zona" con schema LocalBusiness + ficha de Google Business Profile (GBP).

## 0. Nota metodológica (leer primero)

- Se ejecutaron **40 búsquedas web distintas** (inglés y español). Las citas y datos de abajo salen de los extractos que devolvió el buscador sobre cada fuente.
- **Limitación importante:** el proxy de red de este entorno bloqueó la apertura directa (WebFetch) de TODOS los dominios intentados (holisticseo.digital, blog.google, developers.google.com, docs.cloud.google.com, searchengineland.com, wikidata.org, medium.com, wikipedia.org, hobo-web.co.uk, aleydasolis.com, topicalauthority.digital, etc.). Por lo tanto **no pude leer las fuentes primarias completas**; lo que figura como cita textual proviene de los resúmenes de búsqueda. Donde completo con conocimiento previo (corte junio 2026) lo marco como **[CONOCIMIENTO PREVIO – verificar]**. Además, el presupuesto de búsquedas de la sesión se agotó (200/200) antes de terminar la ronda 4, por lo que quedaron 12 consultas sin ejecutar (listadas al final).
- Etiquetas: **[OFICIAL]** = Google/Wikidata/documentación primaria; **[FILTRACIÓN/PATENTE]** = leak 2024 o patentes; **[TEST]** = estudio con datos; **[OPINIÓN]** = experto/agencia sin datos propios; **[posiblemente desactualizado]** = respaldo anterior a 2024.

---

## 1. Koray Tuğberk GÜBÜR (Holistic SEO): el marco y su traducción a reglas para sitios locales

### 1.1 Conceptos (qué dice Koray)

| Concepto | Definición (según fuentes) | Etiqueta / fuente |
|---|---|---|
| Topical Authority (fórmula original) | "Topical Authority = Topical Coverage × Historical Data" (concepto formalizado 18-may-2022). | [OPINIÓN] https://x.com/KorayGubur/status/1917196653213438322 (abr-2025); https://www.holisticseo.digital/theoretical-seo/topical-authority/ [posiblemente desactualizado, 2022] |
| Fórmula expandida | TA = (Topical Coverage × Historical Consistency) ÷ Cost of Retrieval. Koray aclara que "Cost of Retrieval" fue "la verdadera inspiración detrás de topical authority… todo el framework se creó según 'cómo hacer nuestra entidad web más barata para Google'". | [OPINIÓN] mismo tweet abr-2025; https://linkboss.io/topical-authority/ ; https://www.linkedin.com/posts/ehsan-khan-semantic-seo_why-some-websites-rank-without-backlinks-activity-7446105978019905537-f0mZ (2026) |
| Topical Coverage | Cubrir todas las variaciones semánticas y subtemas de un nicho: "procesar todos los atributos de una entidad" y "procesar todas las variaciones de una plantilla de query". | [OPINIÓN] Koray en Search Engine Land, jul-2026: https://searchengineland.com/how-semantics-and-topical-authority-improve-local-seo-482980 |
| Historical Data | Historial de confiabilidad y señales de usuario acumuladas del dominio en ese tema (antigüedad del contenido en el tema, clics, consistencia). | [OPINIÓN] holisticseo.digital (2022) [posiblemente desactualizado] |
| Cost of Retrieval | Cuán barato le resulta al buscador rastrear, entender, indexar y servir el sitio: menos páginas redundantes, menos ambigüedad, HTML liviano, estructura clara. | [OPINIÓN] tweet abr-2025 |
| Source Context | "Identidad de marca o método de monetización": la razón por la que el sitio merece estar en el índice (modelo de negocio + audiencia). | [OPINIÓN] https://topicalmap.services/koray-framework/ ; https://rokonz.com/resources/semantic-seo-glossary |
| Central Entity | El sujeto principal que aparece en todo el sitio; descripción precisa e inequívoca de "de qué es este sitio", categorizable por el buscador. | [OPINIÓN] ídem |
| Central Search Intent | Un enunciado "verbo + sustantivo" que une Source Context y Central Entity; contra él se mide cada tema del mapa. | [OPINIÓN] ídem |
| Core Section / Outer Section | Core = unión de Source Context con Central Search Intent (lo que monetiza). Outer = mejora datos históricos, relevancia temática y "consolidación contextual" (soporte informativo). | [OPINIÓN] https://pos1.ar/koray-framework/ (ES, 2026); https://topicalmap.services/koray-framework/ |
| Macro / Micro Context | Un macro-contexto por página (ángulo principal), varios micro-contextos (subsecciones) que lo desarrollan sin cambiar de tema. "Un macro contexto por página, H2 como preguntas del usuario, respuestas extractivas de ~40 palabras, cobertura EAV completa". | [OPINIÓN] https://digixpertz.com/75-semantic-seo-content-writing-rules-by-koray/ ; https://topicalmap.services/semantic-content-brief-services/ |
| Contextual Vector | Dirección de significado del documento: el orden en que aparecen encabezados/entidades marca el "vector". "Se arreglan con jerarquía, contenido vecino y términos del dominio de conocimiento… para cubrir intents posibles, queries correlacionadas, secuenciales y de búsqueda de entidad". | [OPINIÓN] https://www.holisticseo.digital/theoretical-seo/topical-authority/ [posiblemente desactualizado] |
| Contextual Hierarchy | Jerarquía entre secciones contextuales (H1>H2>H3) alineada a taxonomía + actividad de búsqueda de subtemas. | [OPINIÓN] ídem |
| Contextual Coverage | Cuánto de los contextos posibles de una entidad cubre cada artículo. "Los rankings iniciales vienen de la autoridad de la fuente, vectores contextuales correctos y cobertura en cada artículo". | [OPINIÓN] ídem |
| Contextual Bridge | Vínculo (enlace interno + oración puente) entre dos páginas que comparten contexto; "los enlaces internos deben tener relevancia entre las dos páginas"; nada de "leé más"/"click acá". | [OPINIÓN] https://sitechecker.pro/interview-koray-tugberk-gubur/ ; https://rokonz.com/resources/semantic-content-writing-rules |
| Semantic Content Network | "Red orquestada de micro y macro contextos" armada con briefs para dominar una plantilla de query cubriendo todos sus dominios contextuales. | [OPINIÓN] https://pos1.ar/seo/koray-framework/ |
| Query Network / Query Template | Conjunto de queries derivadas de una plantilla (ej. "[servicio] en [zona]", "cuánto cuesta [servicio]", "[servicio] 24 horas"). Se cubren todas las variantes de la plantilla. | [OPINIÓN] https://github.com/mshahiddigital/koray-semantic-seo-factory (2026) |
| Attribute-based content (EAV) | Entidad–Atributo–Valor: elegir los atributos correctos de la entidad y darles valores exactos en el texto; los atributos dan los H2/H3 y el orden de prominencia. | [OPINIÓN] https://www.holisticseo.digital/seo-research-study/entity-attribute-value (no abierto) |
| Query Augmentation / AI Mode | "No obtenés resultados para la query que escribís, sino para la que Google procesa". AI Mode expande la query por dimensiones contextuales (ej. "azul de metileno" → tinte, medicina, fotosensibilizador). | [OPINIÓN] https://x.com/KorayGubur/status/1929642396016631896 (jun-2025); https://medium.com/@ktgubur/thoughts-on-ai-search-and-ai-based-seo-3a909099e180 (12-sep-2025) |
| Query Responsiveness ≠ Query Relevance | Responsiveness = qué tan directamente responde el pasaje; Koray lo usa para explicar caídas por Helpful Content. | [OPINIÓN] https://x.com/KorayGubur/status/1943088367614255376 (jul-2025) |
| "Si tu documento no puede rankear, tus pasajes no pueden rankear" | Koray sobre la guía de Google para AI Search: AEO/GEO son técnicamente SEO. | [OPINIÓN] https://x.com/KorayGubur/status/2056452254664740896 (2026) |

**Ojo con la afirmación "el core update de octubre 2025 validó la metodología de Koray"** (topicalmap.services, linkboss.io): es marketing de proveedores del framework, sin datos abiertos → [OPINIÓN], no [TEST].

### 1.2 Lo más relevante para Benja: Koray aplicado a SEO local (SEL, julio 2026)

Fuente: https://searchengineland.com/how-semantics-and-topical-authority-improve-local-seo-482980 (Koray Tuğberk GÜBÜR, jul-2026) [OPINIÓN con caso propio].
- "En proyectos de SEO local, procesar una query con sus atributos de ubicación y de servicio, y luego distribuir esos atributos por el documento web, tiene gran importancia."
- Caso: **fusionar páginas [servicio] + [ubicación] innecesarias** mejoró tanto la ficha GBP como la web: "más de 232 queries nuevas y 60 queries con mejor ranking".
- "Semántica visual": Google usa anotaciones como *center-piece annotation* para identificar la función principal del documento → el bloque principal de la página tiene que ser el servicio+zona, no un banner genérico.
- Dos reglas simples: "procesar todos los atributos de la entidad" y "procesar todas las variaciones de la plantilla de query".

**Traducción a reglas prácticas para un sitio de 50–500 páginas de servicio local:**
1. **Source Context explícito:** el sitio es "empresa de [oficio] que vende [servicios] en [departamento/provincia]". Todo lo que no ayude a vender ese oficio en esa zona queda afuera (sube el siteFocusScore, ver §6; baja el "cost of retrieval").
2. **Central Entity = el oficio (ej. cerrajería), no la marca.** La marca es el Source Context. La entidad central atraviesa H1, URL, breadcrumbs, schema y anchors.
3. **Central Search Intent = "contratar cerrajero en [zona]".** Cada página se evalúa contra eso. Si no acerca a la contratación, es Outer Section.
4. **Core Section = páginas transaccionales servicio × zona** (las que monetizan). **Outer Section = soporte informativo** (precios, cómo elegir, problemas, comparativas, normativa). Proporción sugerida por practicantes del framework: ~70/30 a 80/20 core/outer para sitios comerciales chicos [OPINIÓN, no de Koray directamente].
5. **Una página = un macro-contexto.** "Cerrajero en Pocitos" no debe mezclar "cómo abrir una puerta sin llave" (eso es Outer). Sí puede tener micro-contextos: urgencias, cambio de cerradura, precios orientativos en la zona, tiempos de llegada.
6. **Contextual Vector local:** el orden de los H2 debe seguir la secuencia del cliente: problema → servicio → zona/tiempo de llegada → precio → garantía/confianza → FAQ. No arrancar con "quiénes somos".
7. **Contextual bridges:** cada página zona enlaza a (a) su página servicio padre, (b) 2–4 zonas vecinas reales, (c) 1–2 páginas de soporte con anchor descriptivo ("cuánto cuesta cambiar una cerradura en Montevideo"), con una oración que justifique el enlace.
8. **Atributos antes que keywords:** listar atributos de la entidad (tipo de cerradura, marca, tiempo, precio, garantía, horario, zona, urgencia) y asegurar que cada atributo aparece con un VALOR concreto ("llegamos en 30–45 min en Pocitos, Punta Carretas y Buceo"), no con adjetivos.
9. **Cost of retrieval bajo:** evitar 300 páginas zona idénticas; si dos zonas no tienen diferencia real (equipo, tiempos, precios, fotos, reseñas), Koray fusionaría (caso SEL). Mejor 60 páginas únicas que 300 clonadas.
10. **Historical data:** no borrar/renombrar URLs que ya rankean; sumar contenido en el mismo dominio y tema de forma constante (el framework premia consistencia temporal).

---

## 2. Entity SEO 2026, Knowledge Graph, NLP y query fan-out

### 2.1 Query fan-out en AI Mode [OFICIAL]
- Google (I/O, 20-may-2025): AI Mode "usa la técnica de query fan-out: descompone tu pregunta en subtemas y emite una multitud de queries simultáneamente en tu nombre". Deep Search "usa la misma técnica llevada al siguiente nivel: puede emitir cientos de búsquedas, razonar sobre piezas dispares de información y crear un informe experto con citas en minutos". Post: https://blog.google/products-and-platforms/products/search/google-search-ai-mode-update/ (may-2025; no abierto directamente, citado vía https://herdl.com/google-i-o-2025/ y https://surferseo.com/blog/query-fan-out/). Actualización sep-2025: https://blog.google/products/search/search-ai-updates-september-2025/.
- [CONOCIMIENTO PREVIO – verificar] La doc de Search Central "AI features and your website" (may-2025) dice que no hay requisitos extra para AIO/AI Mode: aplican las prácticas SEO estándar, el contenido debe ser rastreable/indexable y elegible para snippets; los datos estructurados deben coincidir con lo visible.

### 2.2 Cuántas sub-queries dispara [TEST]
- 59% de los prompts disparan 5–11 sub-queries, 24% disparan 12–19, cola larga hasta 28 (agregado de estudios 2025-26): https://nobori.ai/blog/query-fan-out-optimization-hidden-sub-queries-ai-citations-2026 ; https://websearchapi.ai/blog/what-is-query-fan-out-and-insights (60.000 queries).
- Seer Interactive: promedio 10,7 sub-queries por prompt en Gemini 3 (501 prompts, 2026), citado en nobori.ai.
- iPullRank: queries de AI Search de 70–80 palabras vs 3–4 en búsqueda tradicional (dic-2025): https://ipullrank.com/ai-search-manual/query-fan-out ; guía práctica https://ipullrank.com/query-fanout-how-to.
- Semrush experimento: al optimizar artículos para sub-queries del fan-out pasaron de 2 a 5 citas (+150%) [TEST chico, sin control]: https://www.semrush.com/blog/query-fan-out-experiment/ (2025). Semrush: "aparecer consistentemente en las fan-out queries subyacentes aumenta la probabilidad de ser citado aun sin ser el top del prompt original".

### 2.3 Citas de AIO vs top 10 orgánico [TEST] — evidencia de que la cobertura de subtemas importa más que la posición
- Ahrefs (2026): sólo 38% de las páginas citadas en AIO están en el top 10 de esa query (era 76% en jul-2025); el resto se reparte entre posiciones 11–100 (31%) y >100 (31%). Ahrefs lo atribuye a "mejor detección de citas" y al "fan-out: Google cita páginas que rinden bien en el clúster ampliado de sub-queries". https://www.searchenginejournal.com/google-ai-overview-citations-from-top-ranking-pages-drop-sharply/568637/ ; https://ahrefs.com/blog/search-rankings-ai-citations.
- Ahrefs: **menciones de marca en la web = predictor #1 de cita en AIO (correlación 0,664)**; longitud del contenido correlación 0,04 (nula); 53% de citas van a páginas de <1.000 palabras. https://ahrefs.com/blog/ai-seo-statistics (2025-26).
- Semrush (200.000 AIO, 2025): overlap AIO–top10 de sólo 20–26%; >80% de AIO móviles incluyen ≤3 URLs del top 10. https://www.semrush.com/blog/ai-overviews-study/.
- BrightEdge (16 meses de AIO): 54% de citas vienen de rankings orgánicos, el crecimiento del overlap viene de posiciones 21–100. https://www.brightedge.com/resources/weekly-ai-search-insights/rank-overlap-after-16-months-of-aio.
- arXiv 2605.14021 (Washington University in St. Louis, 55.393 queries, 13-mar a 21-abr-2026): activación de AIO 13,7% global, **64,7% en queries en forma de pregunta vs 9,5% en no-pregunta** (6,8×); 29,8% de dominios citados no aparecen en la primera página orgánica. https://arxiv.org/abs/2605.14021 [TEST académico].
- Contradicción interna de los datos: BrightEdge (54%) vs Ahrefs (38%) vs Semrush (20-26%). Diferencias de método y período; la tendencia común es que **la posición 1–10 ya no garantiza la cita**.

### 2.4 Entity SEO / Knowledge Graph 2026 [OPINIÓN, guías de agencia]
- Guías 2026 (digitalapplied, stackmatix, contadu, seojetty, clickrank) coinciden en: KG con ~800.000 millones de hechos; "la claridad de entidad determina si aparecés en AIO"; "Gemini se entrena con el Knowledge Graph" (afirmación no verificada oficialmente); paneles de conocimiento para negocios locales "más disponibles desde inicios de 2025". https://www.digitalapplied.com/blog/entity-seo-knowledge-graph-optimization-guide-2026 ; https://contadu.com/semantic-seo-in-2026-nlp-entities-and-knowledge-graphs/ ; https://www.stackmatix.com/blog/entity-based-seo-topical-authority. Tratar como [OPINIÓN]; ninguna aporta test.
- Jason Barnard (Kalicube): "Entity Home" = la URL canónica única que ancla cómo algoritmos y personas entienden la marca (formalizado en SEL, mar-2026); "Entity Corroboration" = terceros confirman los hechos que declarás en tu Entity Home. https://jasonbarnard.com/entity/entity-home-page/ ; https://majestic.com/seo-in-2025/jason-barnard [OPINIÓN].
- Hobo Web "Entity SEO – how to get your business recognised as an entity": https://www.hobo-web.co.uk/entity-seo/ [OPINIÓN].

### 2.5 Entity salience y Google NLP API
- [OFICIAL] Release notes de Cloud Natural Language: desde la v2 (Public Preview 28-ago-2023) el análisis de entidades usa "un nuevo modelo basado en PaLM… sin campo salience" y sin `wikipedia_url`; se agregó `probability`. https://docs.cloud.google.com/natural-language/docs/release-notes. La v1 (con salience) seguía documentada en 2026: https://docs.cloud.google.com/natural-language/docs/reference/rest/v1/documents/analyzeEntities. Tutorial feb-2026 confirma que la API sigue operativa: https://oneuptime.com/blog/post/2026-02-17-how-to-extract-named-entities-from-text-using-the-cloud-natural-language-api/view.
- Conclusión: la API sigue disponible en 2026, pero **"salience" es un concepto de la v1 heredada**; no conviene construir procesos alrededor de ese número [posiblemente desactualizado si Google apaga v1].

### 2.6 "Things to know" [OFICIAL/TEST]
- Feature de segmentación de tema: lista de subtemas derivados de cómo la gente explora el tema (queries de seguimiento, estructuras de contenido). Presencia hasta 45,1% en may-2025; 69,5% en salud. https://www.similarweb.com/blog/marketing/seo/things-to-know/ ; https://kalicube.com/learning-spaces/faq-list/seo-glossary/what-is-googles-things-to-know-feature/. Es una fuente gratuita de subtemas para el mapa temático (ver §5).

### 2.7 Fuentes en español
- pos1.ar (Eduardo Peiro, AR): adaptación del framework de Koray al español con casos LATAM: https://pos1.ar/koray-framework/ ; https://pos1.ar/topical-authority/ ; https://pos1.ar/seo-semantico/ (2026) [OPINIÓN].
- juliandurango.com "Mapa temático SEO: cómo crearlo desde cero [Guía 2026]": https://juliandurango.com/mapa-tematico-seo/ [OPINIÓN].
- publiup.com "Autoridad temática en SEO 2025: arquitectura semántica": https://www.publiup.com/blog/autoridad-tematica-seo-arquitectura-semantica/ ; ranktracker ES: https://www.ranktracker.com/es/blog/topical-maps-seo-and-aeo/ ; seoinhouse.es (enlaces internos → mapas de entidades): https://www.seoinhouse.es/enlaces-internos-en-seo-de-la-transmision-de-autoridad-a-los-mapas-de-entidades/ ; bytheweb.com.ar (AEO + autoridad temática, AR): https://www.bytheweb.com.ar/post/aeo-autoridad-tematica-seo-ai [OPINIÓN]. Común: "la autoridad temática real se construye en 6–12 meses".
- seranking.com/es Knowledge Graph: https://seranking.com/es/blog/google-knowledge-graph/ ; guías SEO local 2026 ES: https://www.ceupe.com/blog/seo-local-guia-completa.html ; https://nort3.com/noticias/seo-local-2026/ [OPINIÓN].

---

## 3. Cómo hacer que Google entienda el negocio como entidad (nombre + servicio + zona)

### 3.1 Qué reconoce Google oficialmente en LocalBusiness [OFICIAL]
Doc: https://developers.google.com/search/docs/appearance/structured-data/local-business (no abierta directamente hoy; extractos vía búsqueda + conocimiento previo).
- **Requeridas:** `name`, `address` (PostalAddress).
- **Recomendadas (tabla oficial, [CONOCIMIENTO PREVIO – verificar]):** `aggregateRating`, `department`, `geo`, `menu`, `openingHoursSpecification`, `priceRange`, `review`, `servesCuisine`, `telephone`, `url`. Usar el subtipo más específico (ej. `Locksmith`, `Electrician`, `HVACBusiness`, `MovingCompany`, `HousePainter`, `RoofingContractor`, `HomeAndConstructionBusiness`, `AutoRepair`/`AutomotiveBusiness`).
- Para qué sirve según Google: alimentar el panel/knowledge card cuando buscan el negocio por nombre y datos como horarios; **no es un factor de ranking**. Mueller: "no hay probablemente ningún beneficio ni daño" en propiedades no documentadas; "recomendamos usar datos estructurados para los elementos que querés ver en resultados… y esos se basan en las propiedades que documentamos". https://www.searchenginejournal.com/google-structured-data-rarely-gives-us-unique-information/389729/ [OFICIAL, 2020, posiblemente desactualizado pero nunca desmentido]; https://gradientgroup.com/google-confirms-that-structured-data-wont-make-a-site-rank-better/.
- **areaServed:** una fuente secundaria (blckalpaca.at) lo describe como "recomendado"; según mi lectura previa de la doc **no figura en la tabla oficial** → tratar como "solo semántica schema.org" hasta verificar. Igual vale ponerlo: es la forma estándar de declarar zona de servicio para un SAB (service-area business).
- **sameAs:** documentado en Organization (https://developers.google.com/search/docs/appearance/structured-data/organization): "algunas propiedades se usan detrás de escena para desambiguar tu organización de otras; otras influyen en elementos visuales como el logo y el knowledge panel"; "Google puede hacer uso general de sameAs y otros datos schema.org". Se pone **una vez** en la home o "quiénes somos", no en todas las páginas. [OFICIAL]
- **knowsAbout, hasOfferCatalog, makesOffer, Service, @id:** NO documentados por Google para ningún rich result → "solo semántica". Mueller (2020) y Stan Ventures (cambios de schema anunciados por Mueller para 2026: https://www.stanventures.com/news/google-john-mueller-schema-update-2026-5719/) confirman que Google lee lo que soporta. Beneficio indirecto plausible pero no probado: consistencia interna y consumo por LLM/otros buscadores. [OPINIÓN]
- **@id consistente:** práctica de grafo (misma URI `https://dominio.uy/#organization` en todas las páginas, y `#localbusiness` por sucursal) para que los nodos se enlacen; Google no lo documenta como señal. [OPINIÓN, estándar JSON-LD]

### 3.2 Recomendación de bloque JSON-LD para Benja (mínimo defendible)
- Home: `Organization` (o directamente `LocalBusiness` subtipo) con `@id`, `name`, `url`, `logo`, `telephone`, `address`, `geo`, `openingHoursSpecification`, `priceRange`, `sameAs` [GBP share URL, Instagram, Facebook, LinkedIn, directorios uy/ar como Páginas Amarillas, Cylex, Infoguía], `areaServed` (lista de `City`/`AdministrativeArea`: "Montevideo", "Canelones", "Ciudad de la Costa"…), `knowsAbout` (opcional, texto o URLs de Wikipedia ES de "Cerradura", "Cerrajería"), `hasOfferCatalog` (opcional, lista de `Service`).
- Página servicio × zona: `Service` con `provider` → `@id` de la org, `serviceType`, `areaServed` = la zona, `url`; más `BreadcrumbList` y `FAQPage` sólo si hay FAQ visible (rich result de FAQ restringido desde ago-2023 a sitios gubernamentales/salud [OFICIAL, posiblemente desactualizado]).
- Regla de oro: **lo marcado debe estar visible en la página** (política de datos estructurados de Google). Si `areaServed` dice 40 barrios y la página no los menciona, es inconsistencia.

### 3.3 NAP, GBP y menciones
- Whitespark Local Search Ranking Factors 2026 (encuesta a 47 expertos, 6-nov-2025) [TEST-encuesta]: señales de GBP = 32% del peso del Local Pack; reseñas 20% (subió de 16% en 2023); **categoría primaria = señal #1 dentro de GBP**; "Google decide para qué queries locales sos elegible leyendo categoría, servicios, descripción y atributos". https://www.brightlocal.com/learn/google-local-algorithm-and-ranking-factors/ ; https://thevalleymarketinggroup.com/blog/google-business-profile-ranking-factors-2026/.
- Regla práctica: el **nombre exacto** (mismo string, sin "Cerrajería X – 24 hs Montevideo" en un lado y "X Cerrajeros" en otro), teléfono y dirección/zona idénticos en web, GBP, schema, directorios y redes. Las guías de entidad 2026 insisten: "variaciones sutiles confunden a Google" [OPINIÓN convergente].
- Menciones en otros sitios: Ahrefs mide correlación 0,664 entre menciones de marca y citas en AIO (§2.3) → para pymes UY/AR: notas en medios locales, cámaras (ej. Cámara de la Construcción, asociaciones de cerrajeros), proveedores (distribuidores de marcas de cerraduras/AC), directorios de barrio, listados de la intendencia.

### 3.4 Wikidata: ¿vale la pena para una pyme? Riesgos
- [OFICIAL] Política de notabilidad (https://www.wikidata.org/wiki/Wikidata:Notability): un ítem es válido si (1) tiene sitelink a un proyecto Wikimedia, o (2) "refiere a una entidad conceptual o material claramente identificable, que pueda describirse con **referencias serias y públicamente disponibles**", o (3) cumple una "necesidad estructural". Hay RFC abiertas de reforma de la política (2025-26): https://www.wikidata.org/wiki/Wikidata:Requests_for_comment/Notability_policy_reform.
- Qué NO cuenta como "serio": bases de datos generadas por usuarios, perfiles promocionales, comunicados, LinkedIn, directorios rutinarios, fuentes sin control editorial. https://whitehatwiki.com/wikidata-explained-what-is-it-is-my-company-notable-enough-and-does-it-help-with-geo/ ; https://corymaki.com/wikidata-wikipedia-entity-building-what-qualifies/ [OPINIÓN].
- Riesgo real: "entradas sin referencias se marcan y borran, a menudo en días"; "la mayoría de los borrados no son por notabilidad sino por reglas editoriales: formato, falta de referencias, contenido promocional". "Una sola referencia externa sólida suele bastar para que sobreviva". https://wikiconsult.com/en/wikidata-effective-strategies-for-companies-institutions-and-communicators ; https://www.mlforseo.com/knowledge-graph-strategy/wikidata-for-brands-notability-criteria-and-a-realistic-path/ [OPINIÓN].
- **Recomendación para Benja:** para una cerrajería o empresa de mudanzas sin cobertura de prensa, **no crear ítem en Wikidata** (será borrado y queda mal). Sólo si el cliente tiene ≥2 notas en medios con control editorial (El País, El Observador, La Nación, Clarín, diarios provinciales). El esfuerzo rinde más en GBP + schema + citaciones + menciones. Jason Barnard coincide en priorizar el "Entity Home" propio y la corroboración: https://jasonbarnard.com/entity/wikidata/.

---

## 4. Topical map para un nicho de servicio: ejemplo cerrajería

### 4.1 Estructura
- **Source Context:** "Cerrajería [Marca], empresa de cerrajeros que vende apertura, cambio e instalación de cerraduras en Montevideo y Canelones, con urgencias 24 hs."
- **Central Entity:** Cerrajería (servicio de cerrajero).
- **Central Search Intent:** "contratar un cerrajero (ya / hoy) en mi zona".
- **Core Section (transaccional, monetiza):** servicio × zona. **Outer Section (informativa):** precios, problemas, comparativas, guías, normativa, marcas.
- **Atributos de la entidad (EAV):** tipo de servicio, tipo de cerradura (cilindro europeo, multipunto, de embutir, electrónica, cerrojo), marca (Yale, Cisa, Mul-T-Lock, Kwikset, Prive), objeto (puerta, portón, auto, caja fuerte, candado, persiana), urgencia (24 hs, feriados), tiempo de llegada, precio/rango, garantía, forma de pago, zona/barrio, horario, matrícula/seguro, método (apertura sin daño/ganzúa/bumping).

### 4.2 Tabla — borrador de topical map (cerrajería, Montevideo)

| Entidad / nodo | Atributo(s) que procesa | Tipo de página | Intención | Ejemplo de URL |
|---|---|---|---|---|
| Cerrajería (central) | todos, resumen; Source Context | Home / pilar transaccional | Comercial-local | `/` |
| Cerrajero en [zona] | zona, tiempo de llegada, servicios disponibles, precio orientativo, reseñas de la zona | Core: servicio-genérico × zona | Transaccional local | `/cerrajero/pocitos/` |
| Apertura de puertas | método sin daño, tiempo, precio, urgencia, tipo de puerta | Core: subservicio (pilar) | Transaccional | `/apertura-de-puertas/` |
| Apertura de puertas en [zona] | zona + los anteriores | Core: subservicio × zona (sólo zonas con demanda real) | Transaccional local | `/apertura-de-puertas/centro/` |
| Cambio de cerradura | tipo de cerradura, marca, precio, garantía, tiempo de trabajo | Core: subservicio | Transaccional | `/cambio-de-cerradura/` |
| Cerraduras de seguridad / multipunto | grado de seguridad, marcas, precio, instalación, comparación | Core (con soporte comparativo) | Comercial-investigación | `/cerraduras-de-seguridad/` |
| Duplicado de llaves | tipo de llave (plana, de puntos, codificada, con chip), precio, tiempo | Core: subservicio | Transaccional | `/duplicado-de-llaves/` |
| Cerrajería automotriz | marca de auto, llave con chip, apertura de auto, precio | Core: subservicio | Transaccional | `/cerrajeria-automotriz/` |
| Cajas fuertes | apertura, cambio de clave, instalación, marcas | Core: subservicio | Transaccional | `/cajas-fuertes/` |
| Urgencias 24 hs | horario, feriados, recargo, zonas cubiertas, tiempo de llegada | Core: subservicio (alta demanda) | Transaccional urgente | `/cerrajero-24-horas/` |
| Precios de cerrajería en Montevideo | rangos por servicio, factores, recargos nocturnos | Outer: soporte de precio | Informativa-comercial | `/precios/` |
| ¿Cuánto cuesta abrir una puerta? | precio, factores, cuándo conviene cambiar la cerradura | Outer: pregunta | Informativa | `/blog/cuanto-cuesta-abrir-una-puerta/` |
| Me quedé afuera de casa: qué hacer | pasos, a quién llamar, qué NO hacer, tiempo | Outer: problema del cliente | Informativa (pre-transaccional) | `/blog/me-quede-afuera-de-casa/` |
| Se trabó la llave / cerradura trancada | causas, solución, cuándo llamar | Outer: problema | Informativa | `/blog/cerradura-trabada/` |
| Perdí las llaves: ¿cambio de cerradura o de combinación? | riesgo, costo, opciones | Outer: decisión | Informativa | `/blog/perdi-las-llaves/` |
| Cilindro europeo vs cerradura multipunto | seguridad, precio, instalación | Outer: comparación | Comercial-investigación | `/blog/cilindro-europeo-vs-multipunto/` |
| Cerradura electrónica vs mecánica | precio, pilas, seguridad, marcas | Outer: comparación | Comercial-investigación | `/blog/cerradura-electronica-vs-mecanica/` |
| Marcas de cerraduras en Uruguay | marca → modelos, dónde se consiguen, precio | Outer: atributo "marca" | Informativa | `/blog/marcas-de-cerraduras/` |
| Cómo elegir un cerrajero confiable | matrícula, presupuesto, garantía, señales de estafa | Outer: confianza (E-E-A-T) | Informativa | `/blog/como-elegir-cerrajero/` |
| Bumping / ganzúa: cómo protegerse | método, cerraduras antibumping | Outer: seguridad | Informativa | `/blog/bumping/` |
| Preguntas frecuentes | mix de atributos | Outer/Core híbrido | Informativa | `/preguntas-frecuentes/` |
| Quiénes somos (Entity Home) | nombre, matrícula, equipo, zonas, sameAs | Entidad | Navegacional | `/quienes-somos/` |
| Zonas cubiertas (índice) | lista de barrios/localidades con enlace | Hub de zonas | Navegacional-local | `/zonas/` |

Regla de tamaño: para 50–500 páginas, la combinatoria "7 subservicios × 40 zonas = 280 páginas" es tentadora pero peligrosa (doorway, ver §7 y Contradicciones). Sugerencia: **servicio-genérico × zona** para todas las zonas con demanda (40–80 páginas), **subservicio × zona** sólo para las 3–5 zonas top y 2–3 subservicios top (15–25 páginas), subservicios sin zona (7–10), soporte informativo (20–40). Total realista 100–160 páginas con contenido diferenciado.

### 4.3 Qué va en cada tipo de página
- **Transaccional (servicio × zona):** H1 "Cerrajero en Pocitos – urgencias 24 hs"; primer párrafo con respuesta directa (qué hacemos, dónde, en cuánto tiempo, teléfono); bloque de subservicios con enlaces a pilares; datos de la zona que sólo un local sabe (calles/edificios típicos, tipos de cerradura frecuentes, tiempo de llegada desde la base); precio orientativo de la zona; reseñas de clientes de esa zona; FAQ corta (3–5) con preguntas locales; CTA. Sin teoría.
- **Informativa (soporte):** H2 en forma de pregunta, respuesta extractiva de 40–60 palabras arriba, luego desarrollo; menciona entidades (marcas, tipos) con valores; termina con un puente contextual a la página transaccional relevante ("Si estás en Montevideo, ver precios y tiempos de cambio de cerradura en tu zona → enlace").
- **Contextual bridges (reglas):** (1) el anchor describe el destino con la entidad + atributo ("cambio de cerradura multipunto"); (2) el enlace va dentro de una oración que comparte contexto con la página destino; (3) informativa → transaccional siempre; transaccional → informativa sólo 1–2 (evitar fugar al usuario en urgencia); (4) zona ↔ zonas vecinas reales (geografía, no lista de 40); (5) breadcrumbs `Home > Servicio > Zona`.

---

## 5. N-grams y entidades co-ocurrentes de un oficio: proceso replicable sin herramientas pagas

### 5.1 Herramientas y estado 2026
- **Google Cloud Natural Language API:** disponible; v1 devuelve `salience`, v2 (PaLM) no (§2.5). Tiene cuota gratuita (5.000 unidades/mes históricamente [CONOCIMIENTO PREVIO – verificar]). Español soportado. [OFICIAL]
- **TextRazor:** plan gratuito de 500 requests/día con todas las funciones (entidades, topics, IDs de Wikipedia/Wikidata). https://pijushsaha.com/semantic-seo/how-to-extract-entities-from-textrazor-free-tool/ ; https://www.textrazor.com/relation_extraction [OPINIÓN/OFICIAL del proveedor].
- **InLinks:** plan gratuito limitado; desde USD 49/mes por 100 páginas; usa KG propio. https://inlinks.com/free-seo-tools/. **SEO Utils** usa Google NLP, TextRazor y Dandelion (~20 idiomas): https://help.seoutils.app/guide/nlp-text-analysis.
- **Python gratis:** spaCy (`es_core_news_md`) para entidades + scikit-learn para TF-IDF/n-grams; guías: https://webfor.com/blog/how-to-do-nlp-entity-analysis-with-four-python-libraries-api/ ; https://www.holisticseo.digital/python-seo/tf-idf-analyse/ ; https://aihelperhub.com/blog/python-seo/automating-keyword-research-with-n-gram-analysis/. Calculadora TF-IDF gratuita en navegador (hasta 5 competidores): https://www.digitaleer.com/seo-tools/tf-idf-calculator/.

### 5.2 Proceso paso a paso (sin pagar), por oficio y país
1. **Semillas:** 10 queries de plantilla: "[oficio] [ciudad]", "[oficio] 24 horas", "[subservicio] precio", "[oficio] cerca de mí", "[problema] qué hacer". Buscar desde Uruguay/Argentina (VPN o parámetro `gl=uy`/`gl=ar`, `hl=es-419`).
2. **Top 10 por query:** guardar URLs (excluir directorios y marketplaces si querés el lenguaje de sitios de oficio; incluirlos si querés el lenguaje de los usuarios en reseñas).
3. **Extraer texto** (Python `trafilatura` o copiar manual), limpiar menús/footers.
4. **N-grams:** unigramas/bigramas/trigramas con `CountVectorizer(ngram_range=(1,3))`, stopwords en español rioplatense (agregar "hs", "tel", "wsp"); rankear por número de documentos del top 10 donde aparece (document frequency), no por frecuencia total. Lo que aparece en ≥5 de 10 documentos es "vocabulario obligatorio" del oficio.
5. **Entidades:** pasar los textos por TextRazor (gratis) o spaCy; agrupar por tipo (marcas, productos, lugares, métodos, normas). Anotar co-ocurrencias: qué entidades aparecen juntas en la misma sección (ej. "cilindro" + "Yale" + "antibumping").
6. **PAA / búsquedas relacionadas / autocompletar / Things to know:** para cada query semilla, copiar People Also Ask (expandir 3 niveles), "Búsquedas relacionadas", autocompletar con letras a–z y con "cuánto / cómo / dónde / por qué / vs / precio", y la caja "Cosas que debes saber" si aparece. Todo gratis, manual o con scripts tipo AlsoAsked-free. Estas preguntas son los H2 de las páginas Outer y las FAQ de las Core.
7. **GBP de competidores:** copiar la lista de "Servicios" y categorías de las 10 fichas top del Local Pack: es el vocabulario de atributos que Google ya asocia al oficio.
8. **Reseñas:** extraer n-grams de 200–500 reseñas de fichas top (lenguaje real del cliente: "vino en 20 minutos", "sin romper la puerta"). Esto alimenta el copy de las páginas zona.
9. **Matriz EAV:** una fila por atributo (de §4.1), columnas: valor en nuestro negocio, aparece en top 10 (sí/no), pregunta asociada, página donde se procesa.
10. **Brief por página:** macro-contexto, entidades obligatorias (≥5 del top 10), 3–6 H2 en forma de pregunta, respuesta directa de 40–60 palabras por H2, puentes contextuales definidos.
11. **Control de calidad post-publicación:** pasar el texto propio por TextRazor/NLP y verificar que las entidades principales sean las mismas que las del corpus competidor y que la zona aparezca como entidad `LOCATION` con peso alto.

### 5.3 Advertencia
- Ninguna de estas herramientas "ve" el Knowledge Graph interno de Google; sirven como proxy. Koray y Mueller coinciden en que lo que rankea es el documento completo, no una lista de entidades: el chequeo NLP es diagnóstico, no objetivo.

---

## 6. Evidencia de que la autoridad temática / cobertura semántica mueve rankings

| Evidencia | Qué muestra | Etiqueta / fuente / fecha |
|---|---|---|
| Leak Google Content Warehouse (may-2024): módulo `QualityAuthorityTopicEmbeddingsVersionedItem` con `siteFocusScore` ("cuánto está enfocado un sitio en un tema"), `siteRadius` ("cuánto se desvían los page_embeddings del site_embedding"), `site2vecEmbeddingEncoded`, `pageEmbeddings`. | Google modela foco temático a nivel sitio y desviación por página. No prueba peso en ranking ni vigencia actual ("pasaron >2 años; pueden estar obsoletos"). | [FILTRACIÓN/PATENTE] https://www.hobo-web.co.uk/topical-authority/ ; https://searchengineland.com/unpacking-googles-massive-search-documentation-leak-442716 (may-2024); https://www.whitepress.com/en/knowledge-base/6170/what-are-site-focus-and-site-radius-metrics ; https://fahlout.com/research/topical-authority (2025) |
| Search Engine Land: al declarar y trabajar autoridad temática, su tasa de citación en IA subió a 2,98% (más del doble de la línea base) mientras sitios editoriales comparables caían; Ahrefs 3,16%, Semrush 5,02%. | Caso propio, sin grupo de control. | [TEST-caso] https://searchengineland.com/guide/topical-authority-protects-from-editorial-traffic-decline (2025-26) |
| Ahrefs: menciones de marca correlación 0,664 con citas AIO; longitud ≈ 0; 38% de citas del top 10. | Autoridad de entidad + cobertura de sub-queries > posición. | [TEST] https://ahrefs.com/blog/ai-seo-statistics ; SEJ 568637 (2026) |
| Semrush experimento fan-out: 2 → 5 citas por artículo (+150%) al cubrir sub-queries. | Cobertura de subtemas en la misma página mueve citas en AI Mode. | [TEST chico] https://www.semrush.com/blog/query-fan-out-experiment/ (2025) |
| Koray, SEL jul-2026: fusión de páginas servicio+zona → +232 queries nuevas, +60 mejoras en GBP y web. | Menos páginas mejor diferenciadas > más páginas clonadas, en local. | [TEST-caso del autor] https://searchengineland.com/how-semantics-and-topical-authority-improve-local-seo-482980 |
| arXiv 2605.14021: 64,7% de activación de AIO en queries-pregunta. | La estructura de pregunta atrae la capa generativa. | [TEST académico] https://arxiv.org/abs/2605.14021 (2026) |
| Whitespark 2026: categoría primaria GBP #1; GBP 32%, reseñas 20% del Local Pack. | En el Pack, la "entidad GBP" pesa más que el contenido del sitio. | [TEST-encuesta] nov-2025 |
| Helpful Content System integrado al core (mar-2024); passage ranking (feb-2021, "mejora ~7% de las queries"). | Evaluación a nivel sitio de utilidad + ranking a nivel pasaje siguen vigentes. | [OFICIAL] https://searchengineland.com/google-march-2024-core-update-rollout-is-now-complete-438713 ; https://searchengineland.com/google-passage-ranking-now-live-in-us-english-search-results-346034 [posiblemente desactualizado] |
| "Google's 2025 Contextual Understanding update" (kisworks, searchanswerlab). | No existe un update oficial con ese nombre → descartar. | [OPINIÓN no verificada] |

Lectura honesta: no hay un estudio controlado 2024-2026 que aísle "autoridad temática" como causa de ranking orgánico clásico en nichos de servicio local. Lo que hay es: (a) filtración que confirma que Google mide foco temático, (b) casos de autor, (c) estudios de citación en IA que muestran que cobertura de subtemas y menciones de marca pesan más que la posición, (d) encuestas locales que ponen a GBP arriba. Para Benja, la combinación "GBP fuerte + sitio enfocado con pocas páginas fuera de tema + cobertura de sub-queries en cada página" está respaldada por convergencia de fuentes, no por un test único.

---

## 7. Passage ranking, helpful content y estructura semántica en 2026 (incl. AIO / AI Mode)

- [OFICIAL] Passage ranking (feb-2021): Google puede rankear un pasaje aislado de una página larga; impacto estimado 7% de queries. Sigue activo; Koray (2026): "si tu documento no puede rankear, tus pasajes no pueden rankear" → el pasaje ayuda, pero el documento y el sitio tienen que ser elegibles.
- [OFICIAL] Helpful content: desde mar-2024 es parte del core ranking system (evaluación a nivel sitio). Consecuencia para sitios locales: 200 páginas zona de relleno arrastran a las 30 buenas.
- [OFICIAL] Política de doorway pages (https://developers.google.com/search/docs/essentials/spam-policies): "múltiples nombres de dominio o páginas dirigidas a regiones o ciudades específicas que canalizan a los usuarios a una misma página". Ejemplo típico citado por practicantes: "Plomero en Austin / Dallas / Houston con párrafos idénticos y ciudad cambiada, sin equipo ni dirección en esas ciudades". Caso reportado: HVAC regional perdió >80% de sus doorway pages tras el core de mar-2024 (-63% tráfico en 30 días) [OPINIÓN-caso: https://netcontentseo.com/article/doorway-pages-what-they-are-why-google-punishes-them-and-how-to-avoid-creating-them-in-2025-193 ; https://ricketyroo.com/blog/location-page-spam/].
- [TEST] Estructura que se cita en AIO (agregado de guías 2026 con datos de terceros; https://rankscope.ai/blog/how-to-rank-in-ai-overviews ; https://www.airops.com/blog/ai-overview-rank ; https://wellows.com/blog/google-ai-overviews-ranking-factors/): pasajes de 134–167 palabras favorecidos; 62% del contenido citado tiene 100–300 palabras; "las primeras 100 palabras de cada sección son el espacio más valioso"; "cada encabezado seguido de una respuesta completa y autocontenida"; listas y tablas parseables. [OPINIÓN con datos no auditados].
- [TEST] arXiv 2605.14021: 64,7% activación en preguntas; 29,8% de dominios citados fuera de la página 1.
- [OPINIÓN] Koray: H2 como preguntas del usuario, respuesta extractiva de ~40 palabras, un macro-contexto por página; "Query Responsiveness" (responder directo) separado de relevancia.
- [OFICIAL – CONOCIMIENTO PREVIO, verificar] Doc "AI features and your website" (may-2025): no hay requisitos técnicos nuevos; se recomienda contenido único y útil, elegible para snippets, datos estructurados coherentes con lo visible, y que la página sea rastreable e indexable.

**Reglas 2026 para las páginas de Benja:**
1. Cada H2 = pregunta real (de PAA/autocompletar) o atributo con valor ("¿Cuánto tarda un cerrajero en llegar a Pocitos?").
2. Debajo de cada H2, 40–70 palabras que respondan solas (nombre de negocio + servicio + zona + dato concreto). Después, detalle.
3. Un pasaje = una idea; párrafos de 2–4 oraciones; tablas para precios y comparativas.
4. La página zona debe poder "sobrevivir" al fan-out: cubrir 5–10 sub-preguntas típicas (precio, tiempo, horario, métodos, garantía, pago, tipos de cerradura, zonas vecinas) en secciones cortas, no en un texto de 2.000 palabras.
5. Nada de FAQ schema en páginas comerciales (sin rich result desde 2023); FAQ visible sí.
6. Ficha GBP con categoría primaria correcta y lista de servicios espejo de las páginas del sitio (misma nomenclatura).

---

## Implicancias para Benja (síntesis operativa)

1. **Definí por escrito Source Context / Central Entity / Central Search Intent por cliente** antes de armar URLs. Sirve de filtro: todo lo que no acerca a "contratar [oficio] en [zona]" es soporte o se descarta.
2. **Arquitectura recomendada por sitio:** Home (entidad) + 6–10 pilares de subservicio + 40–80 páginas servicio-genérico × zona con diferenciación real + 15–25 subservicio × zona sólo en zonas top + 20–40 páginas de soporte (precios, problemas, comparativas, elegir proveedor, marcas) + Quiénes somos (Entity Home) + hub de zonas. Total 100–160 páginas de calidad; llegar a 500 sólo si hay 500 contextos reales (varias ciudades con equipo propio).
3. **Diferenciación de página zona (mínimos):** tiempo de llegada real, precio orientativo local, 2–3 reseñas de esa zona, referencias geográficas concretas, subservicios más pedidos ahí, zonas vecinas enlazadas. Si no podés llenar esos 6 campos con datos verdaderos, no crees la página (fusioná, como en el caso de Koray/SEL).
4. **Schema:** LocalBusiness subtipo específico con `@id`, `sameAs` (GBP, redes, directorios), `areaServed`, `geo`, `openingHoursSpecification`, `priceRange`; `Service` por página con `provider @id` y `areaServed`; `BreadcrumbList`. `knowsAbout`/`hasOfferCatalog` opcionales (sin beneficio documentado, sin daño). Todo coherente con lo visible.
5. **Entidad fuera del sitio:** NAP idéntico en todos lados; categoría primaria de GBP bien elegida (señal #1 del Pack); lista de servicios en GBP espejada con el sitio; 5–10 menciones/citaciones locales con control editorial. **Wikidata: no** salvo cobertura de prensa real.
6. **Proceso de vocabulario (gratis):** top 10 + PAA + autocompletar + Things to know + servicios GBP de competidores + reseñas → n-grams (document frequency) + entidades (TextRazor/spaCy) → matriz EAV → briefs. Repetir por oficio y por país (el léxico UY/AR difiere: "cerrajería" vs "cerrajero", "aire acondicionado split" vs "AA", "yeso" vs "durlock").
7. **Redacción para 2026:** H2 en pregunta, respuesta directa de 40–70 palabras, pasajes autocontenidos de 100–200 palabras, tablas de precios, sin relleno. Es lo que sirve a la vez para passage ranking, AIO y AI Mode (fan-out).
8. **Internal linking = contextual bridges:** anchors con entidad+atributo, oración puente, informativa → transaccional siempre, zonas ↔ zonas vecinas reales; evitar footers con 40 barrios.
9. **Medición:** en Search Console, agrupar queries por plantilla (servicio, servicio+zona, precio, problema) y contar queries nuevas por mes (el KPI que usa Koray) además de posiciones; en GBP, mirar "consultas usadas para encontrarte".
10. **Lo que no hay que prometer al cliente:** que schema o "SEO de entidades" suben rankings por sí solos (Google lo niega), ni que 300 páginas zona son "cobertura temática" (es doorway).

## Contradicciones encontradas (y qué aplicar)

1. **Más páginas zona = más cobertura (framework de "query template" de Koray, y práctica de rank & rent) vs. política de doorway pages de Google + caso del propio Koray fusionando páginas.** Aplicar: cobertura de *contextos*, no de URLs. Crear zona sólo con diferenciación real; en el resto, una página de departamento/ciudad con sección por barrio.
2. **areaServed/knowsAbout/hasOfferCatalog "clave para entidades" (guías de agencia 2026) vs. Mueller: Google sólo lee propiedades documentadas.** Aplicar: incluirlas (costo cero, útil para LLMs y consistencia), pero no invertir horas ni venderlas como factor.
3. **Wikidata "más importante que Wikipedia" (guías ES/EN 2026) vs. política de notabilidad y borrados por falta de referencias serias.** Aplicar: no para pymes sin prensa.
4. **Overlap AIO–top 10: 54% (BrightEdge) vs 38% (Ahrefs) vs 20–26% (Semrush).** Aplicar: no discutir el número; asumir que rankear es necesario pero no suficiente, y cubrir sub-queries.
5. **Salience de Google NLP como métrica de "entidad principal" (guías de entity SEO) vs. Google eliminó salience en el modelo v2 (2023).** Aplicar: usar entidades/co-ocurrencias como diagnóstico; no optimizar hacia un número de salience.
6. **"Un macro-contexto por página" (Koray) vs. "cubrir 5–11 sub-queries del fan-out en la página".** No es contradicción real: las sub-queries son micro-contextos del mismo macro-contexto. Aplicar: secciones cortas que respondan sub-preguntas dentro del mismo tema, sin saltar a otro tema.
7. **Longitud: guías que piden 1.500–2.500 palabras vs. Ahrefs (correlación 0,04; 53% de citas en <1.000 palabras).** Aplicar: página zona de 500–900 palabras densas; soporte informativo según necesidad.
8. **"El core update de octubre 2025 validó a Koray" (vendedores del framework) vs. ausencia de datos públicos.** Aplicar: usar el framework por su lógica operativa, no por esa supuesta validación.

## Pendientes no ejecutados (por bloqueo de red / cupo de búsquedas agotado)
- Abrir y verificar la tabla oficial de propiedades de LocalBusiness (¿areaServed figura?).
- Abrir la doc "AI features and your website" y el post de I/O 2025 para citas literales.
- Abrir el artículo de Koray en SEL (jul-2026) completo: metodología del caso de fusión de páginas.
- Detalle del experimento de fan-out de Semrush (muestra, control).
- Ejemplos de topical maps locales de Koray (dentista/plomero) para calibrar proporción core/outer.
- Método con Knowledge Graph Search API para chequear si el negocio ya es entidad (kgmid).
- Fuentes primarias de holisticseo.digital (topical-authority, topical-map, entity-attribute-value) y glosario rokonz.com.
