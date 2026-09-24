# BLOQUE A — Estado de Google Search 2025–2026
**Para:** Benja (Montevideo) — sitios de servicios locales UY/AR con muchas páginas servicio × zona y dominios EMD
**Fecha de la investigación:** 24 de septiembre de 2026
**Pregunta central:** ¿dónde está la línea exacta entre location pages legítimas y doorway pages / scaled content abuse?

---

## 0. Nota metodológica y limitaciones (leer primero)

- Se hicieron **~60 búsquedas web distintas** (inglés y español). El presupuesto de búsquedas de la sesión se agotó al final (200/200), así que unas pocas verificaciones finales quedaron pendientes y están marcadas.
- **Limitación grave:** el proxy de red de este entorno bloqueó **todas** las descargas de páginas completas (WebFetch) que intenté: `developers.google.com`, `status.search.google.com`, `support.google.com`, `blog.google`, `searchengineland.com`, `seroundtable.com`, `searchenginejournal.com`, `ahrefs.com`, `semrush.com`, `sterlingsky.ca`, `whitespark.ca`, `brightlocal.com`, `gsqi.com`, `ppc.land`, `localsearchforum.com`, `ricketyroo.com`, `hexdocs.pm`, `techcrunch.com`, `en.wikipedia.org`, `x.com`, `web.archive.org`. Es decir: **no pude abrir fuentes primarias completas**; todo lo que sigue proviene de los resúmenes y fragmentos que devuelve el buscador (que citan textualmente a esas fuentes) más mi conocimiento previo hasta mediados de 2026.
- Consecuencia práctica: las "citas literales" de las políticas de spam (punto 3) están reconstruidas a partir de fragmentos que las citan palabra por palabra + conocimiento previo. Coinciden en todos los tramos que los fragmentos confirmaron, pero **hay que verificarlas contra la página oficial antes de usarlas en un documento para cliente**. Lo marco en cada caso.
- Etiquetas: **[OFICIAL]** (Google Search Central, Sullivan, Mueller, Illyes), **[FILTRACIÓN/PATENTE]** (leak Content Warehouse 2024, juicio DOJ), **[TEST]** (estudios con datos), **[OPINIÓN]** (blogs, agencias, casos anónimos). **[posiblemente desactualizado]** cuando el único respaldo es anterior a 2025. **[NO VERIFICADO]** cuando la fuente es de baja autoridad o contradice a otras.

---

## 1. Cronología de updates confirmados 2025–2026

Fuente maestra oficial: `https://developers.google.com/search/updates/ranking` [OFICIAL] (bloqueada para descarga; fechas reconstruidas con Search Engine Land, Search Engine Roundtable, SEJ y el Search Status Dashboard citados en los fragmentos).

### 2025 (3 core + 1 spam, según el balance anual de Search Engine Land)

| Update | Inicio | Fin | Duración | Qué se sabe |
|---|---|---|---|---|
| **March 2025 core update** | 13 mar 2025 | 27 mar 2025 | 14 días | "Regular update designed to better surface relevant, satisfying content for searchers from all types of sites". Google dijo que habría "una serie de mejoras a lo largo del año" para creadores pequeños, pero que **no todos los sitios se van a recuperar del todo**. Volatilidad similar a la anterior (dic 2024) según proveedores de datos. |
| **June 2025 core update** | 30 jun 2025 (07:30 PT) | 17 jul 2025 (01:00 PT) | 16 d 18 h | El update donde por primera vez se vieron **recuperaciones visibles de sitios "HCU"** (ver punto 2). Amsive: Amazon, Target, Wayfair, Best Buy golpeados; sitios con "voz humana clara" subieron. |
| **August 2025 spam update** | 26 ago 2025 | 22 sep 2025 | 27 días | "Broad and general spam update affecting all languages and regions". Se percibió en dos oleadas (24 h iniciales y otra ~9 sep). Analistas lo asocian a scaled content abuse (IA de baja calidad) y site reputation abuse. Sterling Sky documentó un negocio local golpeado (ver punto 5). |
| **December 2025 core update** | 11 dic 2025 | 29 dic 2025 | 18 días | El más disruptivo de 2025. Sistrix: Wikipedia el mayor perdedor (−435 pts); ganadores: especialistas (Thesaurus.com, Trustpilot, retailers de nicho); perdedores: generalistas. SE Ranking: 66,8% de top-3 cambiaron. |

Fuentes: Search Engine Land, "Google algorithm updates 2025 in review: 3 core updates and 1 spam update" (dic 2025) `https://searchengineland.com/google-algorithm-updates-2025-in-review-3-core-updates-and-1-spam-update-466450` [TEST/prensa]; SEL "Google August 2025 spam update done rolling out" (22 sep 2025) `https://searchengineland.com/google-august-2025-spam-update-done-rolling-out-461560`; SER "Google December 2025 Core Update Rolling Out" (11 dic 2025) `https://www.seroundtable.com/google-december-2025-core-update-40569.html`; Sistrix `https://www.sistrix.com/blog/google-december-2025-core-update-information-and-analysis/`; Amsive `https://www.amsive.com/insights/seo/googles-december-2025-core-update-winners-losers-analysis/`.

Otros hitos 2025 que no son "updates de ranking" pero cambian el juego:
- **23 ene 2025** — nueva versión de las Quality Rater Guidelines con criterios explícitos para IA generativa (ver punto 6). [OFICIAL]
- **Ene 2025** — Google empieza a aplicar la política de site reputation abuse en Europa (había arrancado en EE. UU. en mayo 2024). Fuente: SEL/Digital Hitmen (2026) `https://www.digitalhitmen.com.au/blog/googles-site-reputation-abuse-policy-explained/` [OPINIÓN sobre hecho OFICIAL].
- **1 ago 2025** — Danny Sullivan deja de ser Search Liaison (pasa a Director dentro de Search). ppc.land `https://ppc.land/danny-sullivan-no-longer-googles-search-liaison-on-august-1-2025/`; SEL `https://searchengineland.com/danny-sullivan-no-longer-the-google-search-liaison-459864` [OFICIAL vía prensa]. Implicancia: menos declaraciones públicas "de Liaison" en 2026.
- **11 sep 2025** — nueva versión de las QRG (182 páginas; cambios menores, ver punto 6). [OFICIAL]

### 2026 (hasta el 24 sep 2026)

| Update | Inicio | Fin | Duración | Qué se sabe |
|---|---|---|---|---|
| **February 2026 Discover core update** | 5 feb 2026 | 27 feb 2026 | 21 d 17 h | **Primer core update exclusivo de Discover.** Tres objetivos declarados: más contenido localmente relevante (sitios del país del usuario), menos clickbait/sensacionalismo, más contenido original y con expertise "tema por tema". Blog oficial: `https://developers.google.com/search/blog/2026/02/discover-core-update` [OFICIAL]. No afecta Search web. |
| **March 2026 spam update** | 24 mar 2026 (12:18 PT) | ~25 mar 2026 | **19 h 30 min** (el más rápido de la historia) | Anunciado en X por @googlesearchc `https://x.com/googlesearchc/status/2036523482138268071`; incidente en Status Dashboard `https://status.search.google.com/incidents/VbnSXAH4SmEcxPtx4YSD` [OFICIAL]. Sin blog post ni políticas nuevas. |
| **March 2026 core update** | 27 mar 2026 | 8 abr 2026 (09:12 ET) | 12 d 4 h | **El más volátil registrado**: SE Ranking 79,5% de top-3 cambiaron; ~1 de cada 4 páginas top-10 salió del top-100. Patrón: "corrección hacia fuentes de primera mano" — ganan marcas, sitios oficiales/gubernamentales, especialistas; pierden agregadores, directorios, comparadores, UGC (YouTube −567 pts Sistrix, Reddit −64, **Yelp −33**, TripAdvisor −45, Expedia −33). |
| **May 2026 core update** | 21 may 2026 | 2 jun 2026 | ~12 días | Segundo core del año. seoClarity lo llamó "the Disintermediation Update": marcas directas (aerolíneas +8,2%, finanzas +9,5%) suben, agregadores bajan en todos los verticales. 33,7% de keywords con nuevo #1 en la semana previa al anuncio (movimiento empezó antes del anuncio). **Local service businesses mostraron volatilidad baja** (digitalapplied, día 5). |
| **June 2026 spam update** | 24 jun 2026 (09:00 PT) | 26 jun 2026 (10:00 PT) | 2 d 1 h | Status Dashboard `https://status.search.google.com/incidents/YUX1peHev5a4fkxLDiUQ` [OFICIAL]. Sin lista de objetivos. SER reportó (no confirmado por Google) que no apuntaba a link spam ni site reputation abuse, lo que orienta a tácticas de contenido (scaled content, cloaking, keyword stuffing). |
| **August 2026 spam update** | 18 ago 2026 | 21 ago 2026 | 2 d 16 h | SER `https://www.seroundtable.com/google-august-2026-spam-update-41895.html`; SEJ `https://www.searchenginejournal.com/google-begins-rolling-out-the-august-2026-spam-update/586301/`. **Pegó más fuerte de lo normal**: SEL reporta +82% de URLs top-10 que cayeron fuera del top-100 vs. período sin update; 16,71% de URLs top-10 cayeron más allá de la posición 100 `https://searchengineland.com/google-august-2026-spam-update-ranking-impact-485980` [TEST]. Glenn Gabe publicó 4 case studies: scaled content abuse vía IA, **contenido programático**, thin affiliates, actividad maliciosa `https://www.gsqi.com/marketing-blog/august-2026-google-spam-update-case-studies/` [TEST]. |
| ¿August 2026 core update? | ¿26 ago? | ¿21 sep? | ¿26 días? | **[NO VERIFICADO / probablemente falso]**. Solo lo menciona un fragmento de searchenginewatch.com que se contradice con otro fragmento del mismo sitio ("a mediados de septiembre los indicadores de volatilidad no mostraban un update en curso") y con dev.to ("Google logged six ranking updates in 2026" = Discover feb + spam mar + core mar + core may + spam jun + spam ago). Las fechas coinciden sospechosamente con el spam update de agosto 2025 (26 ago–22 sep). **Chequear el dashboard oficial antes de afirmarlo.** |

Otros hitos 2026 relevantes:
- **15 may 2026** — Google **modifica la frase introductoria de las spam policies** para dejar claro que aplican a AI Overviews y AI Mode (ver punto 3 y 7). SEL `https://searchengineland.com/google-updates-search-spam-policies-to-clarify-it-applies-to-generative-ai-responses-477657` [OFICIAL vía prensa].
- **15 may 2026** — Google publica el recurso "Optimizing your website for generative AI features on Google Search" `https://developers.google.com/search/blog/2026/05/a-new-resource-for-optimizing` [OFICIAL].
- **19 may 2026 (I/O)** — Gemini 3.5 Flash pasa a ser el modelo por defecto de AI Mode a nivel global; rediseño de la caja de búsqueda. `https://blog.google/products-and-platforms/products/search/search-io-2026/` [OFICIAL].
- **Abr 2026** — la página de "report spam" ahora dice explícitamente que Google **puede usar reportes de spam para aplicar acciones manuales** (antes decía que solo alimentaban los algoritmos). ALM Corp `https://almcorp.com/blog/google-spam-reports-manual-actions/`; sketchweb (15 abr 2026) `https://micro.sketchweb.net/2026/04/15/google-spam-reports-can-trigger.html` [OFICIAL vía terceros]. **Relevante para Benja: un competidor puede denunciar una red de EMDs.**
- **21 abr 2026** — Search Central Live Toronto (Sullivan, Splitt, Waisberg, Raghavan, Levering). Mensajes: "AI bajó la barrera de creación, Google sube la barrera de indexación"; "Crawled – currently not indexed casi nunca es un problema técnico: suele ser señal de calidad"; "volumen ≠ visibilidad; publicar más (sobre todo con IA) suele empeorar las cosas en 2026"; concepto de **"commodity content"** (contenido que cualquiera puede replicar) vs. contenido único/auténtico. SER `https://www.seroundtable.com/google-commodity-content-41200.html`; slides fotografiadas por JC Chouinard `https://www.jcchouinard.com/google-search-central-live-toronto-slides-april-2026/` [OFICIAL].
- **28 ago 2026** — Blog "Update to the Site Reputation Policy" `https://developers.google.com/search/blog/2026/08/update-site-reputation-policy` [OFICIAL] (ver punto 3).

---

## 2. Helpful Content System después de marzo 2024: ¿se recuperaron los sitios?

**Contexto** [OFICIAL]: en marzo 2024 el "helpful content system" dejó de existir como sistema aparte y se integró al core ranking. Desde entonces no hay "próximo HCU": las señales se recalculan en cada core update. Google lo describió así en el blog de marzo 2024 (no re-descargado; conocimiento previo) [posiblemente desactualizado en la forma, no en el fondo].

**Lo que dijo Google 2024–2025:**
- Oct 2024, Web Creator Summit (Mountain View): Sullivan y Pandu Nayak reconocieron ante ~20 creadores golpeados que muchos sitios "no tenían nada malo" y que **no debían esperar recuperar sus rankings después del siguiente update**. ppc.land `https://ppc.land/googles-web-creator-summit-reveals-challenges-in-helpful-content-system-detection/`; SER `https://www.seroundtable.com/google-search-ranking-update-coming-38323.html` [OFICIAL vía prensa].
- Sullivan (entrevista con Barry Schwartz sobre el August 2024 core update): "the changes have helped some of those sites but generally have not brought those sites all the way back up to the level they were back to say last September"; "you can't predict that every site will recover to exactly where they were in September because September doesn't exist anymore". `https://www.seroundtable.com/interview-google-august-core-update-38024.html` [OFICIAL, dic 2024] [posiblemente desactualizado].
- Mar 2025, al lanzar el March 2025 core update: Google prometió "una serie de mejoras a lo largo de este año" para creadores, pero aclaró que **"not all sites will fully recover with future core updates"**. SEL `https://searchengineland.com/google-not-all-sites-will-fully-recover-with-future-core-algorithm-updates-453507` (mar 2025) [OFICIAL vía prensa].
- 20 mar 2025, Search Central Live NYC: Sullivan dijo que Google "está trabajando para mejorar cómo trata a los sitios pequeños y darles más oportunidades". SER `https://www.seroundtable.com/google-search-central-live-nyc-2025-39104.html` [OFICIAL].

**Evidencia de recuperaciones [TEST]:**
- **June 2025 core update**: Glenn Gabe (GSQi) llamó a las recuperaciones HCU "the biggest surprise" del rollout; sitios "obliterados" por el HCU de sep 2023 "came back from the dead". Seguía una lista de ~400 sitios golpeados. `https://www.gsqi.com/marketing-blog/june-2025-google-core-update/`; SER "Google June 2025 Core Update Recoveries" `https://www.seroundtable.com/google-june-2025-core-update-recoveries-39735.html`; Lily Ray/Amsive vio lo mismo `https://www.amsive.com/insights/seo/june-2025-core-update-winners-losers-trends/`.
- Magnitud: de ~400 sitios trackeados por Gabe, solo **22% tuvo ≥20% de lift** tras el core de agosto 2024, "casi ninguno recuperó del todo"; los "recuperados" típicamente vuelven a ~1/3 del tráfico original; muchos solo al 10–20% (Stan Ventures / SE Ranking / Niche Pursuits, 2025) `https://www.stanventures.com/news/sites-impacted-by-hcu-see-modest-recovery-says-glenn-gabe-1185/`, `https://seranking.com/blog/seo-news-recovery-after-hcu/`.
- Mediavine: de 10.302 sitios, **11,4%** tuvo ganancias reales post-HCU [TEST, vía snippet].
- Raptive (jun 2025): creadores independientes recuperaron visibilidad tras meses de caída `https://raptive.com/blog/what-did-googles-june-2025-core-update-tell-us-about-seo/`.
- Dic 2025 y 2026: el patrón dominante ya no es "HCU vs. no HCU" sino **especialista vs. generalista** (dic 2025) y **primera mano vs. intermediario** (mar/may 2026). Sitios "hechos para el buscador" siguen perdiendo en cada core.

**Lectura para Benja:** el HCS no volvió a existir como "sistema con switch"; lo que hay es un clasificador site-wide integrado al core que se re-evalúa cada 2–3 meses. Las recuperaciones existen (jun 2025 fue el punto de inflexión) pero son parciales y lentas. Un sitio de servicios locales con muchas páginas templadas está expuesto a la señal site-wide de "contenido hecho para rankear", que es la misma familia de señales.

---

## 3. Políticas de spam vigentes (texto y cambios 2025–2026)

URL oficial: `https://developers.google.com/search/docs/essentials/spam-policies` [OFICIAL]. **No pude descargarla** (bloqueo de red). El texto de abajo está reconstruido a partir de fragmentos que la citan palabra por palabra (bulkbase.ai, layer3labs.io, patrickstox.com, ppc.land, digitalhitmen.com.au, SEJ) y de mi conocimiento previo de la página. Las partes que los fragmentos confirmaron literalmente van entre comillas; **verificar contra la página oficial antes de citarlas a un cliente**.

### 3.1 Frase introductoria (cambiada el 15 may 2026) [OFICIAL vía SEL 477657]
> "In the context of Google Search, spam refers to techniques used to deceive users or manipulate our Search systems into featuring content prominently, such as attempting to manipulate Search systems into ranking content highly **or attempting to manipulate generative AI responses in Google Search**."

Cambio: se agregó la referencia explícita a respuestas de IA generativa (AI Overviews / AI Mode). Todas las políticas de abajo aplican también a la visibilidad en esas superficies.

### 3.2 Doorway abuse (texto confirmado por fragmentos)
> "Doorway abuse is when sites or pages are created to rank for specific, similar search queries. They lead users to intermediate pages that aren't as useful as the final destination. Examples of doorway abuse include:
> - Having multiple websites with slight variations to the URL and home page to maximize their reach for any specific query
> - **Having multiple domain names or pages targeted at specific regions or cities that funnel users to one page**
> - Generating pages to funnel visitors into the actual usable or relevant portion of your site(s)
> - Creating substantially similar pages that are closer to search results than a clearly defined, browseable hierarchy"

(Las tres primeras viñetas están confirmadas literalmente por los fragmentos; la cuarta viene de conocimiento previo — verificar.) Cambios 2025–2026: ninguno de fondo detectado. **Ojo con la segunda viñeta: describe casi exactamente el modelo "varios EMDs por ciudad que derivan al mismo negocio".**

### 3.3 Scaled content abuse (texto confirmado por fragmentos)
> "Scaled content abuse is when many pages are generated for the primary purpose of manipulating search rankings and not helping users. This abusive practice is typically focused on creating large amounts of unoriginal content that provides little to no value to users, **no matter how it's created**.
> Examples of scaled content abuse include, but are not limited to:
> - Using generative AI tools or other similar tools to generate many pages without adding value for users
> - Scraping feeds, search results, or other content to generate many pages (including through automated transformations like synonymizing, translating, or other obfuscation techniques), where little value is provided to users
> - Stitching or combining content from different web pages without adding value
> - Creating multiple sites with the intent of hiding the scaled nature of the content
> - Creating many pages where the content makes little or no sense to a reader but contains search keywords
> If you're hosting such content on your site, exclude it from Search."

Historia: introducida el 5 mar 2024 reemplazando "spammy auto-generated content". Cambios 2025–2026: no se detectaron cambios de texto; sí de **aplicación** (spam updates ago 2025, mar/jun/ago 2026; Toronto abr 2026). La viñeta "creating multiple sites with the intent of hiding the scaled nature" es la que más toca a una red de EMDs de un mismo operador.

### 3.4 Site reputation abuse (texto vigente desde nov 2024, clarificado ago 2026)
> "Site reputation abuse is the practice of publishing third-party pages on a site in an attempt to abuse search rankings by taking advantage of the host site's ranking signals. Third-party pages are those published either without close oversight or involvement of the first-party, or with such involvement but with the primary purpose of manipulating search rankings…" (conocimiento previo; los fragmentos confirman la definición resumida: "third-party content is published on a host site primarily because of that host's established ranking signals").

Ejemplos oficiales (conocimiento previo, verificar): sitio educativo con reseñas de préstamos escritas por terceros; sitio médico con página "best casinos" de terceros; sitio de reseñas de cine con contenido de terceros confuso; sitio deportivo con "workout supplements reviews" de terceros; sitio de noticias con cupones provistos por terceros.

Cambios:
- **Nov 2024** — se eliminó la excepción de "supervisión de primera parte" (blog `https://developers.google.com/search/blog/2024/11/site-reputation-abuse`). [OFICIAL]
- **Ene 2025** — enforcement extendido a Europa. [OFICIAL vía prensa]
- **28 ago 2026** — blog "Update to the Site Reputation Policy" `https://developers.google.com/search/blog/2026/08/update-site-reputation-policy` [OFICIAL]: tras discusiones con la Comisión Europea, (a) Google **no aplicará el efecto de acciones manuales de site reputation abuse para usuarios dentro del EEE** desde el 30 ago 2026 (sigue enviando la notificación; en su lugar puede "separar" la sección afectada para que rankee por mérito propio); (b) fuera del EEE la acción manual afecta solo la sección infractora; (c) clarificación: **"no amount of first-party involvement or oversight changes the third-party nature of content if its primary purpose is ranking manipulation"**. SEJ `https://www.searchenginejournal.com/google-updates-site-reputation-abuse-policy-removes-penalties-in-eea/587423/`; SEL `https://searchengineland.com/google-wont-respect-manual-actions-for-site-reputation-abuse-in-european-economic-area-486055`; SER `https://www.seroundtable.com/google-site-reputation-policy-eea-41968.html`.
- Relevancia para Benja: baja (no publica en sitios de terceros), salvo que haga "rank and rent" alojando páginas de clientes dentro de un dominio con autoridad ajena.

### 3.5 Expired domain abuse (texto confirmado por fragmentos)
> "Expired domain abuse is where an expired domain name is purchased and repurposed primarily to manipulate search rankings by hosting content that provides little to no value to users. Examples of expired domain abuse include, but are not limited to:
> - Affiliate content on a site previously used by a government agency
> - Commercial medical products being sold on a site previously used by a non-profit medical charity
> - Casino-related content on a former elementary school site"

Introducida el 5 mar 2024. Sin cambios de texto 2025–2026. La página aclara (conocimiento previo) que usar un dominio vencido para un sitio nuevo, original y pensado para usuarios **está bien**. Caso documentado con nombre: **The Hairpin** (dominio comprado y convertido en granja de contenido IA) — SEJ `https://www.searchenginejournal.com/in-depth-look-at-google-spam-policies-updates/511005/` (2024) [posiblemente desactualizado].

### 3.6 Acciones manuales y reportes (2026)
- Search Console "Manual actions report" `https://support.google.com/webmasters/answer/9044175` lista "Doorways" (más "Thin content with little or no added value", "Site reputation abuse", etc.). [OFICIAL]
- Desde abr 2026 los **reportes de spam pueden derivar en acción manual** (ver punto 1). [OFICIAL vía terceros]

---

## 4. La línea entre location pages legítimas y doorway / scaled content

### 4.1 Lo que dijo Google (personas)

- **John Mueller, dic 2019** (pregunta sobre 1.300 páginas ciudad+servicio): "That sounds like doorway pages, not something I'd recommend." SER `https://www.seroundtable.com/google-city-landing-pages-doorway-pages-28670.html`; Local Search Forum `https://localsearchforum.com/threads/google-city-landing-pages-can-be-doorway-pages-against-guidelines.55438/` [OFICIAL] [posiblemente desactualizado — pero nadie de Google lo contradijo después].
- **Mueller (hangout, ~2017–2018)**: "You can't swap out the city name or a few pictures and then call it good. These local landing pages with duplicated content can be considered doorway pages"; "con local landing pages tenés que crear contenido único relacionado no solo con el área sino con la oficina específica del negocio". Citado por The Media Captain `https://www.themediacaptain.com/location-pages-seo/` [OFICIAL] [posiblemente desactualizado].
- **Mueller, 25 jul 2023**: "programmatic SEO is often a fancy banner for spam". SER `https://www.seroundtable.com/programmatic-seo-banner-for-spam-google-35766.html` [OFICIAL] [posiblemente desactualizado].
- **Mueller (Google Search Central Community, hilo "Spam Policies Doorway Abuse")** `https://support.google.com/webmasters/thread/346436308/spam-policies-doorway-abuse` — no pude abrirlo; fecha aproximada 2025. [NO VERIFICADO]
- **Danny Sullivan (2024, sobre scaled content)**: "The key things are, large amounts of unoriginal content and also no matter how it's created." SEJ `https://www.searchenginejournal.com/google-on-scaled-content-its-going-to-be-an-issue/543308/` [OFICIAL].
- **Search Central Live Toronto, 21 abr 2026** (Sullivan et al.): "commodity content" = contenido que otros ya tienen o pueden replicar fácilmente; "unique content brings a viewpoint, information or has content that others lack or can't easily replicate"; "authentic content demonstrates first-hand knowledge or expertise"; "volume does not equal visibility". SER `https://www.seroundtable.com/google-commodity-content-41200.html` [OFICIAL, 2026]. **Esta es la declaración oficial más reciente y más aplicable a páginas servicio × zona: una página "cerrajero en Pocitos" con el mismo texto que "cerrajero en Carrasco" es commodity content por definición.**
- **Resultado de la búsqueda de declaraciones 2025–2026 específicamente sobre "city pages" / "pages that differ only by city name":** no encontré ninguna nueva de Mueller/Sullivan/Illyes con fecha 2025–2026. La doctrina vigente sigue siendo la de 2017–2019 + la política escrita + los mensajes de Toronto 2026. Marcar como **[posiblemente desactualizado en la forma, vigente en el fondo]**.

### 4.2 Lo que dice la política escrita (ver 3.2 y 3.3)
La combinación de las dos viñetas clave define la línea:
1. Doorway: "multiple domain names or pages targeted at specific regions or cities **that funnel users to one page**" → el problema no es tener páginas por ciudad, es que sean **intermedias** (el usuario termina en el mismo formulario/teléfono/página que en todas las demás y la página en sí no resuelve nada).
2. Scaled content: "many pages … primary purpose of manipulating search rankings … unoriginal content … little to no value … no matter how it's created" → el problema no es la cantidad ni la herramienta, es la **falta de valor diferencial por página**.

### 4.3 Criterios operativos que usa la industria local (2025–2026) [OPINIÓN, consenso]
- RicketyRoo, "Location Pages: What Crosses the Line to Doorway Abuse & Spammy Content?" `https://ricketyroo.com/blog/location-page-spam/`: la línea se cruza cuando la página es "solo un contenedor de keyword" — dice lo mismo que todas las demás y cambia el nombre de la ciudad.
- Manning Search Marketing (2025–2026) `https://www.manningmarketing.com/articles/location-pages-vs-doorway-pages-seo-best-practices-and-pitfalls/`: "una página por dirección física es un objeto distinto de una página por área de servicio; si tenés 12 sucursales, 12 location pages".
- Web Moves, "How Many Service Area Pages Should You Have?" `https://www.webmoves.net/how-many-service-area-pages-should-you-have/` y varios más: "10–15 city pages máximo" como regla de pulgar; más allá "empezás a parecer doorway". [OPINIÓN, sin dato duro]
- Search Engine Land, guía "Service area pages" `https://searchengineland.com/guide/service-area-pages`: la página debe ser "the final destination", contenido "customer-centric", lo más única posible.
- bulkbase / thestacc (2026): "Programmatic SEO está permitido cuando cada página aporta valor real y diferenciado (datos precisos, información local genuinamente útil); viola scaled content abuse cuando las páginas son thin y existen principalmente para rankear".

### 4.4 La contra-evidencia local [TEST]
- **Sterling Sky / Joy Hawkins**: caso de empresa de jardinería con **35 service area pages 85% similares entre sí, todas rankeando bien y generando ventas**. `https://www.sterlingsky.ca/service-area-pages-duplicate-content/` y `https://www.sterlingsky.ca/stop-1000-hours-on-service-area-pages/`. Cita de Hawkins: "I don't think using similar content on different locations is a big deal at all **if you're not targeting the same geographic areas**. After all, there is only so much you can do to get 'unique' content about dental implants for all the thousands of dentists". Fecha del estudio original: pre-2025 [posiblemente desactualizado]. Sterling Sky también recomienda **elegir pocas localidades** (las que tienen demanda real) en vez de cubrir todas `https://www.sterlingsky.ca/pick-locations-for-service-area-pages/`.
- **Sterling Sky, case study August 2025 spam update** `https://www.sterlingsky.ca/august-2025-spam-algorithm-update/` [TEST, sep 2025]: negocio pequeño golpeado; **cayó el orgánico en su patrón de keyword principal, el local pack no se movió**; la caída fue **a nivel de páginas específicas, no site-wide** (muchas páginas del mismo sitio subieron). Infintech (2025) resume: para negocios locales el spam "suele verse como doorway pages — múltiples páginas casi idénticas con solo el nombre de la ciudad cambiado".

### 4.5 Síntesis de la línea (mi lectura, combinando OFICIAL + TEST)
| Señal | Lado legítimo | Lado doorway/scaled |
|---|---|---|
| Destino | La página resuelve la necesidad ahí mismo (teléfono/WhatsApp local, cobertura real, horarios, precios de esa zona) | La página deriva a otra ("llamá a la central", formulario genérico) |
| Diferencia entre páginas | Cambian datos verificables: zonas/barrios cubiertos, tiempos de llegada, tarifas, reseñas de clientes de esa zona, fotos de trabajos ahí, referencias geográficas reales | Cambia solo el nombre de la ciudad y sinónimos |
| Correspondencia con la realidad | El negocio efectivamente atiende esa zona (GBP con service area, reseñas que lo mencionan) | Se cubren 200 localidades donde nunca se hizo un trabajo |
| Arquitectura | Jerarquía navegable: servicio → zona, enlazada desde menú/hub | Miles de URLs huérfanas o solo enlazadas desde un footer |
| Dominios | Un dominio-marca (o pocos, cada uno con negocio real detrás) | Varios EMDs por ciudad del mismo operador que terminan en el mismo teléfono ("multiple domain names… that funnel users to one page" + "multiple sites with the intent of hiding the scaled nature") |
| Volumen vs. demanda | Páginas para zonas con búsquedas y capacidad operativa | Cobertura exhaustiva "por si acaso" |

**Dónde está la línea "exacta":** no existe un umbral numérico oficial (ni de % de similitud ni de cantidad de páginas). Lo más cercano a una regla dura es la propia política: la página es doorway si es **intermedia** (funnel) y es scaled content si es **unoriginal a escala con propósito de rankear**. El test de Sterling Sky muestra que 85% de similitud puede sobrevivir *cuando cada página apunta a una zona distinta y el negocio la atiende de verdad*; el case study de agosto 2025 y los de Gabe 2026 muestran que las mismas páginas caen cuando pierden esa anclita de realidad o cuando el volumen supera lo que el negocio puede sostener.

---

## 5. Casos concretos: penalizados vs. sitios que escalan sin problema

### 5.1 Penalizados / golpeados (documentados)
- **Glenn Gabe, agosto 2026 spam update — 4 case studies** `https://www.gsqi.com/marketing-blog/august-2026-google-spam-update-case-studies/` [TEST, ago–sep 2026]: sitios con "cientos de miles de páginas casi duplicadas o de bajo valor" (scaled content abuse vía IA, **contenido programático**, thin affiliates, actividad maliciosa) con pérdidas masivas de visibilidad. Gabe: la recuperación requiere corregir el spam y luego **varios meses** hasta que Google re-evalúe. No da nombres (anonimiza clientes).
- **Sterling Sky, agosto 2025** (ver 4.4): negocio local pequeño, caída en orgánico de páginas específicas. [TEST]
- **HVAC regional (anónimo)**: cientos de páginas por suburbio con copy casi idéntico; tras el March 2024 core, >80% de esas páginas perdieron rankings y −63% de tráfico orgánico en 30 días; recuperación al **consolidar** en menos páginas por zona con contenido único, reseñas y detalle útil. Citado por Manning, Up North Media, thestacc (2025–2026) [OPINIÓN, caso anónimo, fuente original no identificada].
- **Plomería (anónimo)**: 5.000 páginas "plumber in [city]" que redirigían a un único formulario → **acción manual por doorway pages** a los 4 meses, −96% tráfico, 8 meses y 42.000 páginas borradas para recuperar. thestacc/bulkbase (2026) [OPINIÓN, caso anónimo, NO VERIFICADO].
- **Redes multi-dominio**: "best-austin-plumbers.com + dallas-plumbing-pros.com, thin, del mismo dueño, que derivan al mismo dispatcher → doorway abuse". bulkbase `https://bulkbase.ai/seo/doorway-pages-what-they-are-why-they-hurt-seo` (2026) [OPINIÓN, ejemplo hipotético que calca el modelo EMD-por-ciudad].
- **Site reputation abuse con nombre (2024)**: Forbes Advisor, CNN Underscored, WSJ Buy Side, etc. — Gabe, "A Nightmare on Affiliate Street" `https://www.gsqi.com/marketing-blog/a-nightmare-on-affiliate-street/` [TEST] [posiblemente desactualizado].
- **Expired domain abuse con nombre**: The Hairpin (2024). [posiblemente desactualizado]
- **No encontré ningún caso 2025–2026 con nombre de un sitio de cerrajería/mudanzas/servicios locales penalizado por doorway.** Los casos locales documentados son anónimos (clientes de agencias).

### 5.2 Los que escalan miles de páginas servicio × ciudad
- **Servpro y Roto-Rooter**: ~643.700 y ~652.600 visitas/mes (valor de tráfico ~US$3,1M) con location pages en subcarpetas/subdominios del dominio nacional, contenido "templado con mínima información única — el nombre de la ciudad cambia pero el contenido se lee idéntico entre mercados". PushLeads `https://pushleads.com/how-independent-restoration-companies-can-outrank-servpro-in-local-search/`; Fervor Studio (2026) `https://fervorstudio.ca/contractor/cro-index/roto-rooter/2026-form-placement-mistake/` [OPINIÓN con datos de terceros]. **Por qué no caen:** marca nacional con entidad fuerte, cada página corresponde a una franquicia real con GBP, dirección y reseñas propias; el "commodity content" está compensado por señales de entidad y de negocio real. Google "las trata como parte de una marca nacional, no como negocios locales arraigados" — lo que también es su debilidad frente a un independiente local.
- **Yelp / Angi / Thumbtack**: ejemplos clásicos de programmatic SEO (plantilla por negocio/servicio/ciudad) `https://gracker.ai/blog/10-programmatic-seo-case-studies--examples-in-2025`. **Pero:** son agregadores, y los core updates de mar y may 2026 castigaron precisamente a los agregadores/intermediarios (Yelp −33,1 pts Sistrix en marzo 2026; "Disintermediation Update" en mayo). Lo que los sostiene es que **sus páginas tienen datos únicos** (listados, reseñas, precios) que ninguna otra página tiene. [TEST vía Sistrix/Amsive/seoClarity]
- **Case studies programáticos 2025–2026**: thestacc, 512 páginas → 11.840 clics/mes, sobrevivió a dos updates (may 2026) `https://thestacc.com/blog/programmatic-seo-case-study/`; Concurate, ranking en 60+ ciudades `https://concurate.com/programmatic-seo-case-study/`. Recomendaciones que repiten: **3+ datos únicos por página**, publicar de a 25–30 páginas por semana, construir el hub de enlazado interno antes de escalar, "city pages son el punto de entrada más seguro del pSEO". [OPINIÓN/TEST de agencia]

### 5.3 ¿Qué los diferencia? (síntesis)
1. **Entidad y marca real** detrás (franquicia con GBP por local, reseñas, NAP) vs. EMD sin negocio detrás.
2. **Datos únicos por página** (aunque el texto sea templado) vs. solo texto parafraseado.
3. **Correspondencia con la operación** (atienden esa ciudad, hay reseñas de esa ciudad) vs. cobertura ficticia.
4. **Un dominio con jerarquía** vs. muchos dominios que confluyen en un teléfono.
5. **Volumen proporcional a la demanda y al negocio**: 35–60 páginas de un negocio real sobreviven (Sterling Sky, Concurate); 5.000 páginas de un formulario no.
6. Los agregadores están perdiendo terreno en 2026 frente a marcas de primera mano: **un sitio rank-and-rent con EMD es, a los ojos del algoritmo, un intermediario**, salvo que se convierta en la marca visible del negocio que atiende.

---

## 6. Contenido IA: postura oficial y Quality Rater Guidelines

### 6.1 Guía oficial
- **"Google Search's guidance about AI-generated content"** (feb 2023) `https://developers.google.com/search/blog/2023/02/google-search-and-ai-content` y la página de docs **"Google Search's guidance on using generative AI content on your website"** `https://developers.google.com/search/docs/fundamentals/using-gen-ai-content` [OFICIAL; la segunda es más reciente, 2025]. Puntos: "usar automatización, incluida IA, para generar contenido con el propósito principal de manipular rankings viola las spam policies"; "no todo uso de automatización es spam" (marcadores, clima, transcripciones); la calidad, no el origen, determina el ranking; se recomienda **divulgar cómo se creó el contenido** cuando tenga sentido para la audiencia; E-E-A-T sigue siendo el marco.
- **15 may 2026** — spam policies extendidas a respuestas de IA generativa (ver 3.1) + recurso oficial "Optimizing your website for generative AI features on Google Search" (Semrush lo resume `https://www.semrush.com/blog/google-publishes-generative-ai-search-guide/`). [OFICIAL]
- **Toronto abr 2026**: "publicar más contenido (sobre todo con IA) no arregla la visibilidad; a menudo la empeora"; "Crawled – currently not indexed = señal de calidad". [OFICIAL]

### 6.2 Quality Rater Guidelines — 23 ene 2025 [OFICIAL]
- Nueva definición de **Generative AI** en el glosario y ejemplos.
- **Lowest quality** si "all or almost all of the MC is copied, paraphrased, embedded, auto-generated, or AI-generated with little to no effort, little to no originality, and little to no added value for visitors".
- **Sección 4.6.5 "Scaled content abuse"**: crear mucho contenido "with little effort or originality with no editing or manual curation" → Lowest. Incluye contenido "copiado o parafraseado de distintos sitios", "IA generativa usada de forma low-effort", "filler creado a escala para inflar longitud".
- Matiz clave: **"the use of Generative AI tools alone does not determine"** el nivel de esfuerzo ni la calificación.
- Sección 4.6.6 (conocimiento previo): la falta de originalidad/esfuerzo se juzga también respecto a lo que ya existe en la web para esa consulta.
Fuentes: SER `https://www.seroundtable.com/google-search-quality-raters-guidelines-generative-ai-38842.html` (ene 2025); SEL "Google quality raters now assess whether content is AI-generated" `https://searchengineland.com/google-quality-raters-content-ai-generated-454161` (ene 2025); análisis Fullstackoptimization `https://www.fullstackoptimization.com/a/ai-content-google`; Originality.ai `https://originality.ai/blog/google-search-quality-rater-guidelines-ai`.

### 6.3 Quality Rater Guidelines — 11 sep 2025 [OFICIAL]
- 182 páginas (+1 respecto a la anterior). Google la describió como "a minor update to our rater guidelines with small clarifications and a handful of new examples", sin cambio de criterio.
- Cambios: YMYL amplía explícitamente "Government, Civics & Society" (elecciones/votación); **ejemplos de rating de AI Overviews** (los raters juzgan AIO con la misma consistencia que featured snippets); refinamiento del concepto de "Low quality"; ejemplos claros de cuándo el contenido IA es "Lowest".
Fuentes: SER `https://www.seroundtable.com/google-search-quality-raters-guidelines-update-40092.html`; SEL `https://searchengineland.com/google-updates-search-quality-raters-guidelines-adding-ai-overview-examples-ymyl-definitions-461908`; SEJ `https://www.searchenginejournal.com/googles-updated-raters-guidelines-refines-concept-of-low-quality/545766/`; seo-kreativ `https://www.seo-kreativ.de/en/blog/google-quality-raters-update_9-25/`.

### 6.4 ¿Hubo QRG 2026? [NO VERIFICADO]
- Dos blogs de baja autoridad (pravinkumar.co, broworks.net) hablan de un "June 2026 QRG update" con una "Section 5.2 AI-summarized content = Lowest", "Section 5.4 verifiable real-world expertise" y un flag "Synthetic Authority" en "Section 6.1". **La numeración no coincide con la estructura real de las QRG y ninguna fuente de referencia (SER, SEL, SEJ) lo reporta en los resultados obtenidos.** Otro fragmento afirma que "la versión vigente en 2026 sigue siendo la del 11 sep 2025". Tratar la "QRG junio 2026" como **probablemente inventada** hasta verla en seroundtable.com o en el PDF oficial. No usarla en documentos para clientes.

### 6.5 Traducción a páginas servicio × zona
Una location page generada con IA que parafrasea la de la ciudad vecina cumple simultáneamente: (a) "paraphrased… little effort… little originality" (QRG Lowest), (b) "unoriginal content at scale, no matter how it's created" (scaled content abuse), (c) "commodity content" (Toronto 2026). El uso de IA en sí no es el problema; lo es la falta de **insumo real** (datos de la zona, del negocio, de clientes) que haga que la página no sea parafraseable a partir de otra.

---

## 7. Novedades 2026: AI Mode, presentación de resultados, enforcement

### 7.1 AI Mode y AI Overviews
- **I/O, 19 may 2026** [OFICIAL]: Gemini 3.5 Flash modelo por defecto de AI Mode globalmente; nuevo diseño de la caja de búsqueda (texto, imágenes, archivos, video, pestañas de Chrome); "agentes de información" en Search. `https://blog.google/products-and-platforms/products/search/search-io-2026/`.
- ¿AI Mode "por defecto"? Varios blogs (authoritytech.io, modo25) dicen que I/O 2026 "hizo AI Mode la experiencia por defecto para +1.000M de usuarios". **TechCrunch (27 jul 2026)** `https://techcrunch.com/2026/07/27/googles-ai-search-is-rapidly-becoming-the-default-new-data-shows/` lo plantea como tendencia con datos: visitas a AI Mode 126M (jun 2025) → 279M (may 2026); AI Overviews de 15% → 43% de las búsquedas en un año. Mi lectura: **AI Mode es cada vez más el punto de entrada, pero "default" total no está confirmado por Google en lo que pude ver** [NO VERIFICADO el "default"].
- Para intención local transaccional ("cerrajero urgente Pocitos"), el local pack y los resultados con teléfono siguen siendo la superficie principal; los estudios de mayo 2026 muestran **baja volatilidad para local service businesses** (digitalapplied). Whitespark LSRF 2026 (nov 2025, 47 expertos, 187 factores): GBP 32%, on-page 19%, reseñas 16%, links 15%, behavioral 8%, citas 7%, personalización 3%; suben reseñas y señales de comportamiento `https://whitespark.ca/local-search-ranking-factors/` [TEST/encuesta].

### 7.2 Spam policies aplican a AI Overviews / AI Mode (15 may 2026) [OFICIAL]
- Tácticas como "recommendation poisoning" y listicles sesgados para aparecer en respuestas de IA se consideran spam. Un sitio doorway puede perder visibilidad también en las respuestas de IA. SEL 477657; ALM Corp `https://almcorp.com/blog/google-search-spam-policies-generative-ai-responses/`.

### 7.3 Site reputation abuse 2025–2026
- Ene 2025: enforcement en Europa. Ago 2025 spam update: aplicación algorítmica (analistas). **28–30 ago 2026**: excepción EEE por mandato de la Comisión Europea + clarificación "first-party involvement no cambia la naturaleza third-party". [OFICIAL] (ver 3.4). Uruguay y Argentina **no** están en el EEE: las acciones manuales aplican con efecto completo.

### 7.4 Expired domain abuse y EMD
- Política sin cambios de texto; enforcement "más preciso, no más amplio" en 2026 (Dynadot `https://www.dynadot.com/blog/expired-domains-google-spam-update`) [OPINIÓN]. Criterio operativo: **coherencia temática** entre lo que el dominio fue y lo que aloja ahora.
- EMD: Mueller — "no hay bonus mágico de ranking por EMD" (SER `https://www.seroundtable.com/google-emd-bonus-rank-24108.html`, ~2017) [OFICIAL] [posiblemente desactualizado]; Mueller "cautions against keyword-rich domains" tipo bestplumbernyc.com (SEJ `https://www.searchenginejournal.com/googles-john-mueller-cautions-against-keyword-rich-domains/479777/`, ene 2023) [OFICIAL] [posiblemente desactualizado]. SEL, Carolyn Shelby, "Do exact match domains have value in 2025?" `https://searchengineland.com/exact-match-domains-value-453837` [OPINIÓN, 2025]: los buscadores con LLM priorizan reconocimiento de marca; los EMD "no fueron construidos como marcas". Un estudio 2025 (500 resultados / 51 keywords) encontró EMDs en **25% de los top-3** [TEST, fuente secundaria no identificada — NO VERIFICADO]. Ethical Champ (2026) "EMDs shouldn't work in 2026… but they do" [OPINIÓN].
- Conclusión: el EMD por sí solo ni penaliza ni rankea; el riesgo aparece cuando (a) es un dominio vencido con historial ajeno, o (b) hay **varios EMDs del mismo operador** para ciudades distintas derivando al mismo negocio (doorway) o para esconder la escala (scaled content).

### 7.5 Otras novedades de enforcement 2026
- Reportes de spam → acciones manuales (abr 2026). [OFICIAL vía terceros]
- Spam updates más frecuentes y más cortos (19 h, 2 d, 2 d 16 h) con impacto creciente (agosto 2026 +82% de caídas top-10→>100). [TEST]
- Core updates cada ~2 meses (mar, may 2026) con sesgo hacia fuentes de primera mano. [TEST]
- Filtración Content Warehouse (may 2024) [FILTRACIÓN]: atributos `localityScore` (componente de "LocalAuthority" del sitio), `siteAutopilotScore` (agregado de scores "autopilot" por URL — se especula que detecta sitios automatizados), `smallPersonalSite`, `contentEffort` (estimación LLM de esfuerzo), NavBoost (clics, 13 meses, confirmado bajo juramento por Pandu Nayak en el juicio DOJ). **No encontré un atributo "doorway" explícito** en los resúmenes disponibles. Fuentes: Hobo `https://www.hobo-web.co.uk/the-google-content-warehouse-leak-2024/`; iPullRank `https://ipullrank.com/google-algo-leak`; SEL DOJ `https://searchengineland.com/google-abc-ranking-signals-455360` [FILTRACIÓN] [posiblemente desactualizado: 2024].

---

## Implicancias para Benja

### Confirmado (podés apoyarte en esto)
1. **Location pages por zona son legítimas** siempre que cada una sea "destino final" y aporte información propia de la zona/negocio. Política escrita + Sterling Sky (35 SAPs 85% similares rankeando) + case studies de 60+ ciudades. Nadie de Google dijo en 2025–2026 "no hagan páginas por ciudad".
2. **El uso de IA no es el problema**: QRG ene 2025 ("el uso de IA por sí solo no determina la calificación") + guía oficial. Lo que se castiga es IA sin insumo real (paráfrasis a escala).
3. **La señal se aplica a nivel de página/patrón, no siempre site-wide**: Sterling Sky ago 2025 (cayó un patrón de keyword, el local pack no se movió, otras páginas subieron). Podés perder solo la capa de páginas × zona y conservar el resto.
4. **Local service businesses tuvieron baja volatilidad en los core de 2026**; el local pack depende de GBP/reseñas (Whitespark 2026), no de la cantidad de location pages.
5. **Uruguay y Argentina reciben enforcement completo** (la excepción EEE de site reputation abuse no aplica).

### En riesgo (esto es lo que el método tiene que cambiar o justificar)
1. **Múltiples EMDs por ciudad del mismo operador que derivan al mismo teléfono/WhatsApp**: calza literalmente con la viñeta de doorway abuse ("multiple domain names… targeted at specific regions or cities that funnel users to one page") y con la de scaled content ("multiple sites with the intent of hiding the scaled nature"). Desde abril 2026 un competidor puede reportarlo y Google puede aplicar acción manual. Este es el punto más expuesto del modelo.
2. **Páginas servicio × zona que solo cambian el topónimo**: es "commodity content" (Toronto abr 2026), "paraphrased… little effort" (QRG) y "unoriginal at scale" (política). Los spam updates de 2026 (jun, ago) apuntaron a contenido templado/programático y el de agosto fue inusualmente duro.
3. **Volumen desproporcionado a la operación**: cubrir 100+ localidades donde no hay trabajos hechos ni reseñas. Los casos que sobreviven tienen entre 35 y ~60 zonas con demanda real; los que caen tienen cientos/miles.
4. **Modelo rank-and-rent como "intermediario"**: los core de mar/may 2026 premian fuentes de primera mano y castigan agregadores. Un EMD que no es la marca del negocio se parece más a un intermediario que a un negocio.
5. **Dominios vencidos**: si algún EMD se compró vencido con historial ajeno, expired domain abuse aplica aunque el contenido sea decente si no hay coherencia temática.
6. **Visibilidad en AI Mode/AIO**: las mismas políticas aplican a respuestas de IA (may 2026); una red doorway no va a aparecer citada.

### Qué falta (para una decisión sólida)
1. **Verificar texto literal** de las cuatro políticas contra la página oficial (bloqueada en este entorno).
2. **Confirmar si hubo core update en ago–sep 2026** (una sola fuente, contradictoria) y si existe una QRG 2026 (probablemente no).
3. **Datos propios**: correr un test controlado con dos grupos de páginas × zona (templadas vs. con 3+ datos únicos: barrios cubiertos, tiempo de llegada, tarifa base, 1–2 reseñas de la zona, foto de trabajo) y medir 8–12 semanas. No hay estudio 2025–2026 con umbral de similitud publicado.
4. **Auditar la red de EMDs**: cuántos dominios confluyen en el mismo NAP/teléfono; considerar consolidar en un dominio-marca por negocio con subcarpetas /servicio/zona, y dejar EMDs solo donde haya negocio real y GBP propio.
5. **Recuperar la declaración de Mueller en el hilo "Spam Policies Doorway Abuse"** de Search Central Community (no pude abrirlo).
6. **Buscar fuentes en español con casos UY/AR**: no encontré ninguno documentado; lo que hay son guías genéricas (jmcarreira.net "SEO para cerrajeros: solo 1 por zona", soniacoma.com, top-seo.es "penalizaciones 2026").

---

## Contradicciones encontradas

1. **Mueller (2017–2019): "no podés cambiar el nombre de la ciudad y darlo por bueno" vs. Sterling Sky/Hawkins: "35 páginas 85% similares rankean y venden; contenido similar en zonas distintas no es gran cosa".**
   Recomendación para Benja: aplicar **Google** como regla de diseño y **Sterling Sky** como evidencia de tolerancia. Es decir: diseñar cada página con datos únicos (lo que pide Google), sabiendo que el texto base puede repetirse en gran parte sin castigo *si el negocio atiende la zona y no se apunta a la misma área desde varias páginas/dominios*. El caso Sterling Sky es un negocio único con un dominio; no valida una red de EMDs.

2. **"10–15 city pages máximo" (varios blogs 2025–2026) vs. Servpro/Roto-Rooter con miles de location pages templadas rankeando y case studies de 60+ ciudades.**
   Recomendación: ignorar el número mágico. El límite es operativo, no numérico: tantas páginas como zonas con demanda real y capacidad de atención comprobable. Una franquicia tiene un local real por página; Benja tiene que poder demostrar lo mismo (reseñas, trabajos, GBP con service area).

3. **Yelp/Angi/Thumbtack como "ejemplos de pSEO que funciona" vs. datos Sistrix/Amsive/seoClarity 2026: los agregadores pierden (Yelp −33 pts en marzo 2026).**
   Recomendación: aplicar los datos 2026. Lo que sostiene a esos sitios son datos únicos y marca; lo que los está hundiendo es ser intermediarios. Un rank-and-rent debe posicionarse como la marca de primera mano del negocio, no como directorio.

4. **"Google no penaliza EMDs" (Mueller, política) vs. "Mueller advierte contra dominios keyword-rich" (2023) y SEL 2025 "los LLM priorizan marca".**
   Recomendación: ambas son ciertas y no se contradicen en el fondo: el EMD no resta ni suma por sí mismo; suma la marca. Usar EMD solo si va a operar como marca (un dominio por negocio, con GBP y reseñas), nunca como red de dominios por ciudad.

5. **Sullivan 2024 ("no esperen recuperar") vs. junio 2025 (recuperaciones "back from the dead").**
   Recomendación: las dos son correctas en su momento; la lección es que las recuperaciones llegan con core updates posteriores (6–20 meses) y son parciales. Si un sitio de Benja cae por patrón doorway, planificar corrección + espera de 2–3 core updates.

6. **"June 2026 QRG update" (blogs menores) vs. "la versión vigente es la del 11 sep 2025" (otros).**
   Recomendación: tratar la QRG 2026 como no confirmada; citar solo ene 2025 y sep 2025.

7. **"August 2026 core update (26 ago–21 sep)" (searchenginewatch) vs. "sin señales de update a mediados de septiembre" (mismo sitio) y "seis updates en 2026" (dev.to).**
   Recomendación: no afirmarlo hasta verlo en `developers.google.com/search/updates/ranking`.

8. **Manual actions por doorway "siguen aplicándose activamente" (blogs 2026) vs. ausencia total de casos con nombre 2025–2026.**
   Recomendación: asumir que el riesgo principal en 2025–2026 es **algorítmico** (spam updates + clasificador de calidad integrado al core), con acción manual como riesgo secundario que creció desde abril 2026 (reportes de spam).
