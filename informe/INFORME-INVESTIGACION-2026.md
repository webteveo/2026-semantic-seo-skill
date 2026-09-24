# Informe de investigación — SEO y GEO para sitios de servicios locales, 2026

Preparado para Benja (Webteveo, Montevideo). Fecha de corte: 24 de septiembre de 2026.
Estructura: método y límites → bloques A–H (hallazgos etiquetados, fuentes, contradicciones) → qué cambió 2024→2026 → diagnóstico del método actual. Los anexos por bloque, con todas las fuentes y el detalle, están en `bloques/A-…H-….md` (≈ 2.900 líneas). La versión condensada que usa la skill está en `../seo-local-semantico-2026/references/investigacion-2026.md`.

## 0. Método y límites (leer antes de citar)

- Se ejecutaron **~180 búsquedas web** en inglés y español repartidas en 8 bloques paralelos, más 8 búsquedas de verificación cruzada sobre las afirmaciones que sostienen reglas duras (Toronto 2026, retiro de FAQ, informe de IA en GSC, AI Mode en español, acción manual de Sterling Sky, Whitespark 2026, AIO en búsquedas locales, Koray en SEL 2026).
- **Limitación grave**: la política de red del entorno bloqueó la apertura directa de casi todos los dominios (developers.google.com, support.google.com, searchengineland.com, seroundtable.com, sterlingsky.ca, whitespark.ca, brightlocal.com, ahrefs.com, semrush.com, arxiv.org…). Solo se pudieron abrir de primera mano repositorios de GitHub: espejos textuales de la documentación de Google Search Central (scrape del 8 jun 2026), el vocabulario oficial de schema.org (release 30.1), el repo del paper GEO, C-SEO Bench, AutoGEO, ai.robots.txt, listas de referrers de LLM, docs de Cloudflare, Anthropic y web-vitals. Todo lo demás proviene de los resúmenes y fragmentos que devuelve el buscador (que citan texto literal de las páginas) más conocimiento previo marcado como tal.
- Consecuencia: las citas entre comillas de documentos de Google coinciden con los fragmentos obtenidos, pero **deben cotejarse contra la URL original antes de usarlas en un entregable a cliente**. En cada bloque se listan los pendientes de verificación.
- Etiquetas: `[OFICIAL]` Google/OpenAI/Anthropic/Perplexity/schema.org; `[FILTRACIÓN/PATENTE]` leak Content Warehouse 2024, juicio DOJ, patentes (atributos, no pesos); `[TEST]` estudio con datos; `[OPINIÓN]` consenso sin datos; `[posiblemente desactualizado]` solo respaldo pre-2025; `[NO VERIFICADO]` fuente dudosa o contradictoria.

---

## A. Estado de Google Search 2025–2026

### A.1 Cronología de updates
Ver tabla completa en `bloques/A-google-2026.md` §1. Resumen: 2025 tuvo core en marzo, junio (primeras recuperaciones HCU, parciales), agosto (spam, 27 días) y diciembre (el más disruptivo: especialistas suben, generalistas bajan). 2026: Discover core (feb), spam (24 mar, 19 h), core (27 mar–8 abr, el más volátil registrado, ganan fuentes de primera mano, pierden agregadores: Yelp −33 Sistrix), core (21 may–2 jun, "disintermediation", baja volatilidad en local services), spam (24–26 jun), spam (18–21 ago, inusualmente duro; Glenn Gabe documentó casos de scaled content por IA y **contenido programático**). Un "core de agosto/septiembre 2026" aparece en una sola fuente contradictoria: `[NO VERIFICADO]`.
Fuentes: developers.google.com/search/updates/ranking `[OFICIAL]`; searchengineland.com/google-algorithm-updates-2025-in-review-…-466450; seroundtable.com/google-august-2026-spam-update-41895.html; searchengineland.com/google-august-2026-spam-update-ranking-impact-485980 `[TEST]`; gsqi.com/marketing-blog/august-2026-google-spam-update-case-studies/ `[TEST]`.

### A.2 Helpful Content System después de marzo 2024
`[OFICIAL]` Integrado al core; no vuelve como sistema con interruptor. Sullivan (oct-2024, mar-2025): "no todos los sitios se van a recuperar del todo". `[TEST]` Junio 2025 trajo recuperaciones "back from the dead" (Gabe, Ray), pero parciales: de ~400 sitios, 22 % con ≥ 20 % de mejora; típicamente vuelven a ~1/3 del tráfico. En 2026 el eje ya no es HCU sino "primera mano vs intermediario".

### A.3 Políticas de spam vigentes (texto reconstruido de fragmentos; cotejar en developers.google.com/search/docs/essentials/spam-policies)
- **Frase introductoria (15 may 2026)** `[OFICIAL vía SEL 477657]`: spam incluye "attempting to manipulate generative AI responses in Google Search".
- **Doorway abuse**: "sites or pages created to rank for specific, similar search queries. They lead users to intermediate pages that aren't as useful as the final destination." Ejemplos: "multiple websites with slight variations to the URL and home page"; "**multiple domain names or pages targeted at specific regions or cities that funnel users to one page**"; "generating pages to funnel visitors into the actual usable or relevant portion of your site(s)"; "substantially similar pages that are closer to search results than a clearly defined, browseable hierarchy".
- **Scaled content abuse** (mar-2024, reforzado en enforcement 2025–2026): "many pages … for the primary purpose of manipulating search rankings and not helping users … unoriginal content that provides little to no value to users, **no matter how it's created**". Ejemplos: IA sin valor; scraping con "synonymizing, translating, or other obfuscation techniques"; "**creating multiple sites with the intent of hiding the scaled nature of the content**"; páginas con keywords sin sentido.
- **Keyword stuffing**: "**blocks of text that list cities and regions** that a web page is trying to rank for".
- **Expired domain abuse**: dominio vencido reutilizado para contenido de poco valor; un sitio nuevo y útil en dominio vencido está permitido.
- **Site reputation abuse**: 28 ago 2026 Google dejó de aplicar el efecto de acciones manuales en el EEE; **Uruguay y Argentina reciben enforcement completo**. Poco relevante para Benja salvo alojar páginas de terceros.
- **Abril 2026** `[OFICIAL vía terceros]`: la página de reporte de spam dice que los reportes **pueden derivar en acción manual**.

### A.4 La línea entre location pages legítimas y doorway
- `[OFICIAL] [posiblemente desactualizado]` Mueller 2017–2019: "you can't swap out the city name or a few pictures and then call it good"; sobre 1.300 páginas ciudad+servicio: "that sounds like doorway pages". Mueller 2023: "programmatic SEO is often a fancy banner for spam". No hay declaración nueva 2025–2026 y nadie la desmintió.
- `[OFICIAL, 21 abr 2026]` Search Central Live Toronto: "commodity content" = lo que otros tienen o pueden replicar; contenido "unique, specific, authentic"; "volume does not equal visibility"; "publicar más, sobre todo con IA, suele empeorar"; "Crawled – currently not indexed casi nunca es técnico, es señal de calidad". seroundtable.com/google-commodity-content-41200.html ; jcchouinard.com/google-search-central-live-toronto-slides-april-2026/
- `[TEST]` Contra-evidencia: Sterling Sky, negocio con 35 service area pages 84–85 % similares, todas rankeando y vendiendo; Hawkins: "no es gran cosa si no apuntás a la misma zona geográfica". Caveats: no en mercados muy competitivos; "el riesgo es thin, no duplicado".
- `[TEST]` Sterling Sky, caso de **acción manual por thin content en un sitio con más de 3.000 location pages, con redacción distinta en cada una** (el dueño había pagado redactores humanos). sterlingsky.ca/thin-content-manual-penalty/
- Síntesis (tabla de señales legítimo vs doorway en `bloques/A-google-2026.md` §4.5 y en la skill): no hay umbral numérico; la página es doorway si es **intermedia** y scaled si es **unoriginal a escala**. El 85 % de similitud sobrevive cuando cada página apunta a una zona distinta, el negocio la atiende y el 15–20 % restante son datos.

### A.5 Casos
Penalizados/golpeados (anónimos): HVAC regional con cientos de páginas por suburbio, −63 % tras core mar-2024, recuperó consolidando; plomería con 5.000 páginas a un formulario, acción manual doorway `[OPINIÓN, NO VERIFICADO]`; Gabe ago-2026, sitios programáticos con cientos de miles de páginas `[TEST]`. Sin casos con nombre de cerrajería/mudanzas 2025–2026.
Escalan sin problema: Servpro / Roto-Rooter (miles de location pages templadas) porque cada página es una franquicia real con GBP, dirección y reseñas propias; Yelp/Angi/Thumbtack por datos únicos por página, pero pierden como agregadores en 2026. Diferencia: entidad real, datos únicos, correspondencia con la operación, un dominio con jerarquía, volumen proporcional a la demanda.

### A.6 Contenido IA y Quality Rater Guidelines
`[OFICIAL]` Guía de contenido con IA generativa: la calidad manda, no el origen; automatizar para manipular rankings viola scaled content abuse; recomienda divulgar cómo se creó cuando tenga sentido. **QRG 23 ene 2025**: definición de IA generativa; Lowest si el contenido principal es "copied, paraphrased, embedded, auto-generated, or AI-generated with little to no effort, little to no originality, and little to no added value"; sección 4.6.5 scaled content abuse; Lowest obligatorio si la página existe solo para beneficiar al dueño; Low por "información exagerada o levemente engañosa sobre el sitio o el creador". Matiz: "the use of Generative AI tools alone does not determine" la calificación. **QRG 11 sep 2025** (182 págs.): minor update (YMYL cívica, ejemplos de AIO). **"QRG junio 2026"**: solo blogs menores con numeración que no coincide con el documento → `[NO VERIFICADO / probablemente inventada]`.

### A.7 Novedades 2026
AI Mode con Gemini 3.5 Flash por defecto (I/O 19 may 2026); AIO 15 % → 43 % de las búsquedas en un año (TechCrunch jul-2026); "AI Mode default" no confirmado por Google. Whitespark LSRF 2026. Spam policies extendidas a IA. Reportes de spam → acciones manuales. Leak: `localityScore`, `siteAutopilotScore`, `contentEffort`, NavBoost; sin atributo "doorway" explícito.

### Contradicciones del bloque A y qué aplicar
1. Mueller ("no cambies la ciudad y listo") vs Sterling Sky (35 páginas 85 % similares rankean): diseñar con la regla de Google (datos únicos), sabiendo que el texto base puede repetirse si cada página apunta a una zona atendida de verdad. Sterling Sky es un negocio con un dominio; no valida una red de EMDs.
2. "10–15 city pages máximo" vs Servpro con miles: el límite es operativo (zonas con demanda y operación comprobable), no numérico.
3. Agregadores como "pSEO que funciona" vs datos 2026 (agregadores pierden): un rank and rent con EMD es, para el algoritmo, un intermediario, salvo que sea la marca visible del operador.
4. "EMD no penaliza" vs "Mueller advierte contra keyword-rich domains" y "LLMs priorizan marca": el EMD no suma ni resta por sí; suma la marca. Un dominio por negocio, nunca red por ciudad.
5. "QRG junio 2026" vs cobertura de SER/SEL: citar solo ene y sep 2025.
6. Acciones manuales "activas" vs cero casos con nombre 2025–2026: el riesgo principal es algorítmico; el manual creció desde abr-2026 por reportes.

---

## B. E-E-A-T y cómo Google decide quién es el experto
Detalle en `bloques/B-eeat-leak.md`.

- `[OFICIAL]` QRG vigente 11 sep 2025. Secciones relevantes: 2.5.3 (quién es responsable; About/contacto), 3.3 (reputación externa; para negocios chicos la falta de reputación no penaliza, la negativa sí), 3.4 ("Trust is the most important member of the E-E-A-T family"), 4.5.1/4.5.3 (Lowest por ocultar o fingir identidad/propósito), 5.x (Low por E-E-A-T inadecuado o información exagerada). Cerrajería, electricidad y casas contenedores: "may be YMYL" `[OPINIÓN sobre base OFICIAL]`.
- `[OFICIAL]` "Creating helpful, reliable, people-first content": Who / How / Why; "Does your site have a primary purpose or focus?"; "Is the content mass-produced … or spread across a large network of sites?".
- `[OFICIAL]` Sullivan 2024: Google no verifica bylines ni credenciales; E-E-A-T no es un score.
- `[TEST]` Whitespark 2026, Ahrefs 2025 (menciones de marca > backlinks para visibilidad en IA), Lily Ray dic-2025 (el foco es intención y satisfacción, no señales de autor).
- `[FILTRACIÓN/PATENTE]` Information Gain: US 11,354,342 B2 (7 jun 2022) mide novedad respecto de documentos que el usuario **ya vio**; la lectura "vs top 10" es extrapolación de la industria, útil como heurística editorial (≥ 5 datos que el top no tiene). Posts que la llaman "señal #1 de 2026": marketing.
- `[FILTRACIÓN/PATENTE]` Leak: siteAuthority; siteFocusScore/siteRadius (favorece sitios de un solo servicio); NavBoost (13 meses; goodClicks/badClicks/lastLongestClicks); chard/tofu/keto y contentEffort (calidad por contenido); hostAge (sandbox para "fresh spam"); titlematchScore a nivel sitio; OriginalContentScore (pesa en páginas cortas); exactMatchDomainDemotion; LocalWWWInfo/brickAndMortarStrength/localityScore. Todo son atributos guardados, no pesos ni vigencia confirmada.
- `[OFICIAL – testimonio]` DOJ: NavBoost desde 2005, 13 meses, "one of the important signals"; tres pilares Body/Anchors/User interactions; Q* casi estático; RankEmbedBERT con logs + raters; Glue/Instant Glue para el local pack; remedios (2 sep 2025) obligan a compartir datos.
- Rank and rent: viable = marca de plataforma honesta + operador actual nombrado con foto y matrícula + fotos de trabajos + reseñas en el GBP del operador; prohibido = GBP del rentista o ficticio (lead-gen no elegible), autor inventado, fotos stock como equipo, reseñas fabricadas, sitios clonados por ciudad.

Contradicciones: E-E-A-T "no es factor" vs "señal más fuerte 2026" → aplicar lo oficial (proxies); "domain authority no existe" vs siteAuthority → asumir señal de sitio que arranca en cero; patente vs lectura de industria → heurística; sandbox negado vs hostAge → hay sandbox para spam fresco; CTR negado vs NavBoost → actuar como si contara; Whitespark (reseñas/comportamiento) vs modelo EMD+on-page → sin ficha legítima del operador, el techo es el orgánico.

---

## C. SEO semántico y SEO de entidades
Detalle en `bloques/C-semantico-entidades.md` (incluye tabla de topical map y proceso de n-grams en 11 pasos).

- `[OPINIÓN, Koray Gübür]` TA = (Cobertura × Datos históricos) ÷ Costo de recuperación; Source Context, Central Entity, Central Search Intent, Core/Outer, macro/micro contexto, contextual vector/hierarchy/coverage, bridges, EAV. **SEL jul-2026**: "procesar todos los atributos de la entidad" y "todas las variaciones de la plantilla de query"; **fusionar páginas servicio+zona innecesarias → +232 queries nuevas y +60 mejoras**; "fewer, more purposeful pages". searchengineland.com/how-semantics-and-topical-authority-improve-local-seo-482980 ; searchengineland.com/query-templates-topical-authority-484676 ; searchengineland.com/visual-semantics-topical-authority-482254
- `[OFICIAL]` Query fan-out (I/O may-2025). `[TEST]` ~10,7 sub-queries por prompt; Semrush: cubrir sub-queries 2 → 5 citas (test chico).
- `[TEST]` Overlap citas AIO / top 10: Ahrefs 38 % (era 76 %), Semrush 20–26 %, BrightEdge 54 %; menciones de marca r = 0,664; longitud r = 0,04; arXiv 2605.14021: 64,7 % de activación de AIO en queries-pregunta.
- `[OFICIAL]` LocalBusiness: `name` + `address` requeridas; `Service`/`areaServed`/`knowsAbout`/`hasOfferCatalog`/`@id` no documentados para rich results; `sameAs` para desambiguar. Google Cloud NLP v2 sin `salience`. Wikidata: no para pymes sin prensa.
- `[FILTRACIÓN]` siteFocusScore/siteRadius/site2vec confirman medición de foco temático a nivel sitio.
- No existe un "Contextual Understanding update 2025" ni validación pública del framework de Koray por un core update: marketing de proveedores.

Contradicciones: más páginas = más cobertura vs doorway + caso de fusión de Koray → cobertura de contextos, no de URLs; schema semántico "clave" vs Mueller → incluir a costo cero, no vender como factor; Wikidata; overlap 54/38/20 → rankear es necesario, no suficiente; salience; longitud 1.500–2.500 vs r = 0,04 → páginas de zona de 500–900 palabras densas.

---

## D. Location pages 2026
Detalle en `bloques/D-location-pages.md` (15 reglas duras propuestas, 7 contradicciones).

- `[TEST]` SEL may-2024: la SERP orgánica local pasó de páginas genéricas a casi solo service area pages. `[TEST]` Sterling Sky: bloques que subieron tráfico y ranking: tabla de trabajos recientes en la zona, indicaciones/tiempo desde la oficina, fotos de la zona, reseñas de esa zona. 80/20 boilerplate/local funciona a ~35 páginas; >3.000 con texto distinto → manual; 200 páginas IA → crawled-not-indexed; ChatGPT "falló épicamente" en hiperlocal.
- `[OPINIÓN]` Rangos: Whitespark 10–15; Bipper 15–30 en tandas de 5–10/semana; LSF sin límite "solo cuando hay algo que decir"; nadie avala 500–2.000.
- `[OFICIAL – Illyes]` Google no indexa todo; muchas "crawled – not indexed" = problema de calidad del sitio; spike de desindexación fines de may-2025 `[TEST]`; crawl budget no aplica a < 10k URLs.
- `[OFICIAL]` Dedup por checksum del contenido central sin boilerplate; "Google chose different canonical" en páginas de ubicación plegadas.
- `[OFICIAL – Mueller]` URL = señal mínima; profundidad de clics, no de barras. `[OPINIÓN]` `/zona/` en EMD mono-servicio correcto; `/servicio/zona/` en multi; evitar `/zona/servicio/` y slugs planos a escala.
- `[OPINIÓN de referente]` Sterling Sky: página por servicio distinto, fusionar variantes; canibalización de la búsqueda implícita.
- `[TEST]` Sterling Sky 2025 (8.186 negocios): el pack lo manda la proximidad; ocultar dirección correlaciona negativamente; el área declarada no mueve ranking; páginas de zona no meten la ficha en el pack lejano; rankean en orgánico y sobre todo en localidades con SERP propia.

Veredicto: escalar a 500–2.000 páginas por sitio no es seguro con la evidencia disponible; 30–50 por servicio con umbral de datos, tandas de 5–10, páginas madre por departamento con secciones para localidades sin demanda, sí. Ver reglas en la skill.

---

## E. Estructura on-page
Detalle en `bloques/E-onpage.md` (fórmulas y ejemplos completos; 11 contradicciones).

- `[OFICIAL]` H1 múltiples permitidos; doc de title links pide "main title" distintivo en el "first visible `<h1>`"; blog 2021: titles "half-empty" se completan con el H1. → un H1 alineado con el title.
- `[TEST]` Reescritura de titles: Zyppy 61,6 % (51–60 caracteres = menor tasa; pipe > guion; H1 = title reduce); SEL Q1-2025 76 % (marca eliminada 63 %). Descriptions 63–71 %. `[OFICIAL]` "no hay límite, se trunca por ancho": title ≤ 580 px desktop, ~496 px móvil; description 120–150.
- `[OFICIAL]` Gatillos: largo, marca, keyword repetida, **"boilerplate titles"** (varían en un solo dato), separador, mismatch con H1, emojis (SearchPilot: Google borró emoji + keyword).
- `[FILTRACIÓN]` titlematchScore a nivel sitio; NavBoost/CRAPS (goodClicks, badClicks, lastLongestClicks, 13 meses) → title y hero prometen lo mismo.
- `[OFICIAL]` Keyword stuffing incluye "blocks of text that list cities and regions"; anchors internos sin penalización por sobre-optimización (Illyes 2020, Mueller abr-2025).
- `[TEST]` Conversión: NN/g 57 % de la atención above the fold; Chartbeat 29 % no scrollea; contacto visible +54 % leads; Unbounce 2024 lectura simple 11,1 % vs 5,3 %; conteo de reseñas +28–33 %; quitar testimonios −35 % (casos viejos). No existe estudio "WhatsApp vs formulario" en servicios locales: dato a generar con `click_wsp`.
- `[OFICIAL]` Rich results 2026: FAQ retirado para todos (7 may 2026); HowTo (sep-2023); sitelinks search box (nov-2024); 7 tipos (jun-2025); review snippet self-serving inelegible (reafirmado 10 dic 2025). Quedan Breadcrumb, LocalBusiness/Service, site name, sitelinks.
- Patrones del mercado hispano 2025–2026 (HTML real): "Servicio en Zona 24 hs | gancho (llegamos en X min / desde $X) – Marca"; CTA "por WhatsApp" en description; matrícula como gancho en CABA; teléfono en title (España) se corta y Google lo quita.

---

## F. GEO / AI search
Detalle en `bloques/F-geo-ia.md` (checklist, tabla de crawlers, regex, protocolo de relevamiento).

- `[PAPER]` GEO (KDD 2024): citas a fuentes, citas textuales y estadísticas +30–40 % en Position-Adjusted Word Count; keyword stuffing −10 %; tono autoritativo sin efecto; los prompts admiten citas/estadísticas inventadas; el "+115 %" es el caso de una fuente en 5.º lugar. `[PAPER]` C-SEO Bench (NeurIPS D&B 2025): "most current C-SEO methods are largely ineffective"; rankear en el contexto del LLM es mucho más efectivo; juego de suma cero. `[PAPER]` AutoGEO (ICLR 2026): preferencias distintas por motor. Papers 2026 sobre volatilidad de citas y defensas contra GEO manipulativo.
- `[TEST]` Overlap con top 10: AIO ~38 %; Perplexity ~28,6 %; ChatGPT 6–8 % (28,3 % de las páginas más citadas por ChatGPT sin visibilidad orgánica); AIO y AI Mode coinciden 13,7 %. Tráfico referido de IA (Statcounter abr-2026): ChatGPT 76,9 %, Gemini 9 %, Perplexity 7,7 %, Copilot 3,8 %, Claude 2,7 %.
- `[TEST]` CTR: Pew jul-2025 8 % vs 15 %; Seer sep-2025 −61 % orgánico, +35 % si citado; Ahrefs dic-2025 −58 % en posición 1.
- `[TEST]` Whitespark 2026 (540 consultas): AIO 68 % vs pack 39 %; transaccionales simples AIO 15 % / pack > 90 %; informacionales 92 %; híbridas 97 %. AI Mode no muestra pack; tarjetas de GBP/Maps; nombra 1–3 negocios ("32 % de negocios únicos vs pack").
- `[OFICIAL]` AIO en 200+ países y 40+ idiomas (may-2025); AI Mode en español desde 7 oct 2025 (Argentina nombrada; Uruguay dentro de "200+ territorios", verificar la pestaña "Modo IA"). No existe estudio de AIO en consultas locales en español: dato a generar.
- `[TEST]` Reddit traducido automáticamente = 52–73 % de las citas de Reddit en AIO en mercados no ingleses (mar–jun 2026); ChatGPT lo cortó en may-2026.
- `[OFICIAL]` Crawlers: Googlebot alimenta AIO/AI Mode; Google-Extended solo entrenamiento; OAI-SearchBot = citas en ChatGPT search; ChatGPT-User y Perplexity-User pueden ignorar robots.txt; Claude-SearchBot/Claude-User; Bingbot = Copilot y probablemente ChatGPT. `[TEST]` Vercel/MERJ: ningún crawler de IA ejecuta JS salvo Gemini vía Googlebot.
- `[OFICIAL]` GA4 canal "AI Assistant" nativo desde 13 may 2026 (sin Perplexity). GSC "Generative AI performance": anunciado 3 jun 2026, global 31 ago 2026, impresiones por URL/país/dispositivo, datos desde 18 may 2026, sin clics ni consultas.
- Humo: llms.txt (Mueller jun-2025, Illyes jul-2025, Ahrefs 97 % sin requests), "AI schema", ai.txt, herramientas GEO con puntajes, "+115 %", "60 % de citas de Reddit" (pico de ago-2025 que colapsó).
- Frameworks (Indig, Solis, Huang, King, Volpini, Siege, Semrush, Ahrefs, Peec) convergen en: rankear en el índice fuente; pasajes answer-first autocontenidos con datos y fecha; entidad consistente (GBP + schema + menciones); presencia en fuentes de terceros que la IA ya cita; medir con referrers + GSC.

---

## G. Local SEO 2026
Detalle en `bloques/G-local-2026.md` (tablas de directorios UY y AR con URL, tipo, prioridad y estado de verificación).

- `[TEST-encuesta]` Whitespark LSRF 2026 (nov-2025, 47 expertos, 187 factores): pack = GBP 32 %, reseñas 20 % (era 16 %), on-page 19 %, enlaces 15 %, comportamiento 8 %, citaciones 7 %, personalización 3 %; categoría primaria #1; "abierto al momento de buscar" top 5; nueva sección de visibilidad en IA. Orgánico local: on-page + enlaces siguen siendo la mayoría (tabla 2026 no obtenida; 2023: 36 % + 26 %).
- `[TEST-encuesta]` BrightLocal LCRS 2026: 98 % lee reseñas; 41 % siempre; 68 % exige 4+ (era 55 %); 31 % exige 4,5+; Google baja 83 → 71 %; IA para elegir negocios 6 → 45 % (pregunta redefinida).
- `[OFICIAL]` GBP: chat y call history eliminados 31 jul 2024; Q&A y posts siguen sin anuncio de retiro; verificación por video por defecto (SAB: vehículo rotulado, herramientas, RUT/BPS o AFIP-ARCA); SAB: dirección oculta, área ≤ ~2 h, hasta 20 zonas, una ficha por base física con personal; lead-gen no elegible; keyword stuffing en el nombre, oficinas virtuales, fichas duplicadas y ráfagas de reseñas = suspensión; restricción de reseñas con banner desde 2025.
- `[OFICIAL]` Google demandó (mar-2025) a una red de fichas falsas (10.000+ eliminadas; cerrajeros y grúas); 240 M de reseñas eliminadas en 2024.
- `[TEST]` Sterling Sky: el área de servicio no es señal; el radio lo fija la dirección verificada; servicios cargados no mueven el pack pero alimentan justificaciones e IA; para una sola ubicación, enlazar la home desde la ficha rinde igual o mejor `[posiblemente desactualizado]`.
- Rioplatense: barrios/localidades > gentilicios; "24 hs / urgencias / a domicilio" como atributos y H2, no en el nombre; léxico UY vs AR (fletes, durlock, tinglado); AIO y AI Mode en español activos.
- Directorios: en UY alcanza con ~8–10 (GBP, Facebook, Instagram, Apple Business Connect, Bing Places, Cybo, Yelu, Cylex, Infoisinfo, Páginas Amarillas si vigente); en AR sumar Habitissimo (leads + reseñas indexadas), Páginas Amarillas AR, CAMARCO/INCOSE. Solo Cybo, Yelu, Uruguay-Directorio, DirectoriosEmpresas y Uruguay XXI aparecieron en búsquedas de sesión; el resto requiere verificación manual (checklist en el anexo).

---

## H. Técnico mínimo, schema, imágenes IA, enlazado
Detalle en `bloques/H-tecnico-schema.md` (plantillas JSON-LD, robots.txt, snippet de `click_wsp`).

- `[OFICIAL]` CWV: LCP ≤ 2,5 s, INP ≤ 200 ms, CLS ≤ 0,1 (CrUX p75); "no single signal"; contenido relevante gana aunque la experiencia sea sub-par. Mobile-first cerrado (5 jul 2024).
- `[OFICIAL]` Sitemaps 50k/50 MB; `lastmod` solo si verificable; `priority`/`changefreq` ignorados. Indexing API solo JobPosting/BroadcastEvent (doc 16 jul 2026); Mueller 23 may 2025: "spammers misuse … stick to documented use-cases"; Illyes: revocación sin aviso. IndexNow: Bing, Yandex, Naver, Seznam, Amazon; Google no. Crawl budget: guía para 1 M+ páginas o 10k+ con cambios diarios.
- `[OFICIAL]` schema.org 30.1: subtipos válidos y ausentes (tabla en la skill); `ProfessionalService` deprecado; no existe `ContactAction` (WhatsApp como `ContactPoint.url` / `CommunicateAction`). Google: "no special schema.org structured data" para IA. `[TEST]` Ahrefs may-2026: agregar JSON-LD no subió citas (AIO −4,6 %).
- `[OFICIAL]` FAQ rich results retirados 7 may 2026; review snippet self-serving inelegible; breadcrumb vigente (desktop).
- `[OFICIAL]` Imágenes IA: sin política de spam específica; Illyes: "doesn't impact the SEO. Not direct"; Google lee IPTC `DigitalSourceType` y C2PA. Riesgo: engaño y duplicación.
- `[OFICIAL]` Enlaces: toda página importante con ≥ 1 enlace interno; sin número máximo. `[TEST]` Zyppy: 40–44 entrantes ≈ 4× clics; variedad de anchors = correlato más fuerte. `[FILTRACIÓN]` Reasonable surfer.
- `[OFICIAL]` Cloudflare defaults 15 sep 2026 bloquean bots Training/Agent en páginas con anuncios y anteponen robots.txt gestionado. ccTLD = señal fuerte; IP no determinante; International Targeting retirado; hreflang solo con versiones por país.

---

## Qué cambió de 2024 a 2026 y obliga a hacer algo distinto

1. **Enforcement más frecuente y duro contra scaled content y doorway** (spam updates cada 2–3 meses; ago-2026 golpeó contenido programático) y **reportes de spam que pueden generar acción manual** (abr-2026). La red de EMDs por ciudad al mismo WhatsApp es el patrón más expuesto del modelo.
2. **Google formalizó "commodity content"** (Toronto abr-2026) y sube la barrera de indexación: más páginas iguales empeoran; "crawled – not indexed" es veredicto de calidad. Publicar en tandas y medir indexación pasa a ser obligatorio.
3. **Los cores de 2026 premian fuentes de primera mano** y castigan intermediarios/agregadores. El rank and rent debe convertirse en la marca visible del operador (o nombrarlo como operador actual).
4. **Las spam policies aplican a respuestas de IA** (may-2026) y Google publicó su guía de optimización para IA: sin trucos, es SEO. GSC mide impresiones en IA por URL desde ago-2026.
5. **FAQ rich results desaparecieron** (may-2026): la FAQ vale como contenido, no como schema. Estrellas propias siguen inelegibles.
6. **AI Overviews y AI Mode en español** operan en AR (y casi seguro UY): muerden en informacionales/híbridas (92–97 %) y casi nada en transaccionales simples (15 %). El contenido informacional con precios locales fechados es el activo GEO; en urgencias sigue mandando el pack.
7. **Reseñas y comportamiento pesan más** (Whitespark 2026: reseñas 20 %); 68 % de consumidores exige 4+; la IA justifica recomendaciones con el texto de las reseñas.
8. **GBP endureció**: video por defecto, crackdown a fichas falsas en cerrajería/grúas, lead-gen prohibido. La ficha es del operador real o no es.
9. **Las menciones de marca** predicen citas en IA más que backlinks o longitud → entidad consistente + presencia en terceros.
10. **Los crawlers de IA no ejecutan JS** y Cloudflare bloquea bots por defecto: hay que revisar robots.txt y el HTML inicial.

## Diagnóstico del método actual de Benja

**Confirmado (seguir igual)**
- Contenido + enlaces como núcleo; una URL por intención; un servicio por página; keyword en URL/title/H1; referencias locales reales; todo relativo al top 5; naturalidad; MVP primero; ranking vs conversión vs trámite. Todo tiene respaldo 2025–2026.
- Páginas por **localidad con SERP propia** (Punta Ballena, Balneario Solís, Las Piedras, Pando, Piriápolis) rankean sin local físico: SEL 2024, Whitespark, Sterling Sky y tu caso de cerrajeromaldonado.com.
- Sitio de nicho mono-servicio con EMD: alineado con "primary purpose or focus" y con siteFocusScore; el EMD no penaliza por sí mismo.
- WhatsApp como CTA principal, arriba y sticky, medido en GA4: coherente con toda la evidencia de conversión; además podés generar el dato "WhatsApp vs formulario" que el mercado no tiene.
- URL `dominio/zona` en EMD mono-servicio: correcta; no reestructurar.
- Casas contenedores (posición 2–3, ~250 clics a WhatsApp/mes): es además el vertical con más potencial GEO (informacional, precios por m², permisos).

**En riesgo (cambiar o justificar)**
- **La escala de páginas por zona**: funciona mientras el 20 % local sea real. Miles de páginas con texto distinto pero sin datos terminaron en acción manual; los spam updates de 2026 pegaron a contenido programático. Nueva regla: URL solo con demanda y datos; el resto como sección de la madre; tandas con umbral de indexación; tope operativo 30–50 por servicio y sitio en fase 1.
- **La red de 12+ EMDs**: si comparten plantilla de texto, bloques de zona o teléfono, calzan con dos ejemplos literales de la política. Cada dominio necesita operador, NAP y contenido propios; consolidar donde no los haya.
- **Titles boilerplate en serie y listas de barrios** (footer, párrafos "cerrajero en X, cerrajero en Y"): nombrados literalmente por Google.
- **Imágenes IA** presentadas como trabajos, equipo o local: E-E-A-T roto y riesgo legal de publicidad engañosa; usar solo como ilustración con alt honesto.
- **Fichas GBP para rank and rent**: solo del operador real, verificadas por video; nunca múltiples por zona ni oficinas virtuales.
- **Indexing API** para páginas de servicio (si se usaba): fuera de política, acceso revocable.

**Faltaba (agregar)**
- Tabla de datos por zona como condición de existencia de la URL (`assets/brief-zona.md`).
- Topical map con core/outer y páginas de soporte (precios, problemas, comparativas, marcas, cómo elegir) para autoridad temática y citas en IA.
- Entidad: "Quién te atiende" real, NAP idéntico, schema con `@id` y `sameAs`, menciones en terceros; en rank and rent, el operador actual nombrado.
- GEO: pasajes answer-first con datos y fecha; Bing Webmaster + IndexNow + Bing Places + Apple; canal GA4 "AI Assistants"; informe de IA en GSC; protocolo mensual de prompts; revisión de robots.txt/Cloudflare.
- Control de indexación por tandas con sitemaps segmentados y umbral de "crawled – not indexed".
- Auditoría trimestral de fusión (301) y actualización de precios/fechas.

## Pendientes de verificación con acceso web completo
- Cotejar texto literal de spam policies, title-link, snippet, review-snippet, LocalBusiness, Indexing API y ai-optimization-guide en developers.google.com.
- Abrir el PDF de las QRG (sep-2025) y confirmar secciones 2.5.3, 3.3, 3.4, 4.5, 4.6.5, 5.x.
- Whitespark LSRF 2026: tabla de orgánico local y sección de IA. BrightLocal LCRS 2026: cifras de recencia y cantidad mínima.
- Confirmar si hubo core update en ago–sep 2026 en el dashboard oficial.
- Verificar la pestaña "Modo IA" y AIO desde IP de Uruguay y Argentina en queries del nicho.
- Verificar vigencia y tipo de enlace de cada directorio UY/AR (tablas del anexo G).
- Correr un test propio: dos grupos de páginas de zona (templadas vs con 3+ datos únicos), 8–12 semanas, indexación + impresiones + `click_wsp`.
