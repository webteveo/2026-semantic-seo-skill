# BLOQUE E — Estructura on-page: títulos, encabezados, meta, URL y orden de secciones

**Para:** Benja (Montevideo) — sitios de servicios locales (cerrajería, mudanzas, electricistas, yeso, aire acondicionado, casas contenedores, pérgolas) en Uruguay y CABA.
**Tipos de página:** home · troncal de servicio · servicio + zona. **CTA principal:** WhatsApp (evento GA4 `click_wsp`).
**Fecha de investigación:** 24 de septiembre de 2026.

## 0. Nota metodológica (leer primero)

- Se hicieron **16 búsquedas web distintas** (WebSearch, mínimo pedido: 12) antes de que la sesión agotara la cuota de búsquedas (200/200 compartidas con la sesión madre). Las 6 búsquedas de SERP en español ("cerrajero Pocitos", "cerrajero Palermo CABA 24 horas", "cerrajero Madrid 24 horas urgente", "cerrajero Montevideo urgencias", "title SEO local", "meta description CTR estudio español") **no se pudieron ejecutar**: quedaron en cola cuando la cuota ya estaba agotada.
- **WebFetch estuvo bloqueado por el proxy de egreso para todos los dominios probados** (developers.google.com, searchengineland.com, zyppy.com, searchpilot.com, semrush.com, ahrefs.com, moz.com, brightlocal.com, nngroup.com, cxl.com, baymard.com, unbounce.com, sistrix.com, seroundtable.com, searchenginejournal.com, portent.com, backlinko.com, bing.com, duckduckgo.com, wikipedia.org y ~25 más: 45 intentos, 0 éxitos).
- Para acceder igual a **fuentes primarias**, se usó la búsqueda de código de GitHub (herramienta permitida) sobre **espejos textuales** de: la documentación de Google Search Central (title-link, snippet, spam policies, blog 2021 sobre títulos), la nota oficial de baja de FAQ rich results (citada textualmente desde el doc FAQPage), el módulo filtrado `QualityNavboostCrapsCrapsClickSignals` (espejo de hexdocs en `jroakes/Google-Data`), el atributo `titlematchScore` (`QualityNsrNsrData`), el capítulo SEO del Web Almanac 2024 de HTTP Archive, y **HTML real de sitios de cerrajeros/mudanzas/electricistas en español** (title, description, H1). Son 8+ fuentes primarias abiertas por vía indirecta.
- Cada hallazgo lleva etiqueta: **[OFICIAL]** (Google), **[FILTRACIÓN/PATENTE]**, **[TEST]** (split test o estudio con datos), **[OPINIÓN]** (práctica/consenso sin dato duro). Cuando el respaldo es viejo o no se pudo verificar en esta sesión: **[posiblemente desactualizado]** / **[no verificado en esta sesión]**.
- Las citas de estudios de terceros (Zyppy, McAlpin/SEL, Seer, Portent, Unbounce, NN/g, Google/Ipsos) provienen de los resúmenes de búsqueda y de espejos que los citan, no de la lectura directa del artículo. Se indica URL + fecha igual.

---

## 1. Postura oficial de Google sobre H1 múltiples y jerarquía de encabezados

### 1.1 Lo que dice Google

- **[OFICIAL]** Google no exige un único H1 ni una jerarquía perfecta. John Mueller (Google), frase textual repetida en varios Office Hours y en Twitter: *"Our systems don't have a problem when it comes to multiple h1 headings on a page… You can use H1 tags as often as you want on a page. There's no limit, neither upper nor lower bound."* Respuesta en Twitter a "¿cuántos H1 en una página?": *"As many as you want."* — Fuentes: https://www.searchenginejournal.com/google-h1-headings-seo/328459/ (2019, reafirmado 2020–2025) y https://www.safaridigital.com.au/blog/multiple-h1-tags-for-seo/ (2025). [posiblemente desactualizado en la forma, no en el fondo: Google no cambió esta postura hasta 2026].
- **[OFICIAL]** Mueller también dijo que un sitio *"rankea perfectamente bien sin H1 o con cinco H1"* y que Google usa los encabezados *"para entender mejor el contexto de las distintas partes de la página"*, no como factor de posicionamiento fuerte. — https://seranking.com/blog/john-mueller-google/ (recopilación 2025).
- **[OFICIAL]** La doc de *title links* (developers.google.com/search/docs/appearance/title-link, leída vía espejo `lesishu/seo-guide-skill/references-google/title-link.md`, actualización 2026) dice textualmente: *"Make it clear which text is the main title for the page. Google looks at various sources when creating title links, including the main visual title, heading elements, and other large and prominent text, and it can be confusing if multiple headings carry the same visual weight and prominence. Consider ensuring that your main title is distinctive from other text on a page and stands out as being the most prominent on the page (for example, using a larger font, putting the title text in the first visible `<h1>` element on the page, etc)."* → **Esto es lo más cercano a "un H1 principal" que dice Google, y lo dice por el title link, no por ranking.**
- **[OFICIAL]** Blog Search Central, sept. 2021 "More info about titles" (espejo `sosreader/seo-knowledge-insight/raw_data/google_blog_markdown/2021-09-more-info-about-titles.md`): *"Our system is designed to detect half-empty titles and adjust by looking at information in header elements or other large and prominent text on the page."* → Si el `<title>` es pobre, **Google va al H1**. Por eso title y H1 deben ser coherentes.

### 1.2 Lo que funciona en la práctica

- **[TEST]** SearchPilot, "Split testing titles and H1s: do they still have an SEO impact?" (https://www.searchpilot.com/resources/blog/testing-titles-and-h1s-seo-impact, 2024–2025): concluyen que *"Google still relies on well-optimized H1 and title tags, and even small, data-driven changes to these can make a difference"*. Caso de un sitio de viajes: **agregar precio al H1 y alinear el H1 con el title** para reducir reescrituras (https://www.searchpilot.com/resources/case-studies/adding-price-to-h1). Los % exactos no se pudieron leer (fetch bloqueado) [no verificado en esta sesión].
- **[TEST]** Zyppy / Cyrus Shepard, estudio de 81.000 títulos (2022, reanalizado 2025): *"matching the H1 to the title tag seems to be an effective strategy"* para reducir reescrituras de title. — https://zyppy.com/seo/google-title-rewrite-study/ (citado vía `benjaminoakes/www.benjaminoakes.com`, 2022-01-29).
- **[OPINIÓN]** Consenso de herramientas: Ahrefs no tiene chequeo de "múltiples H1"; Semrush lo marca como *Notice* (no afecta Site Health); Screaming Frog "Warning (Medium)"; Sitebulb "Low"; Lighthouse no lo audita. — Log de verificación `digibranders/cleanstart-web/docs/seo/11-semantics-accessibility-overlap.md` (2026-07-29).
- **[OPINIÓN]** Accesibilidad (WCAG / BOIA): un solo H1 sigue siendo mejor práctica para lectores de pantalla y para dejar claro el tema de la página. — https://www.boia.org/blog/multiple-h1-tags-are-bad-for-accessibility-and-seo.

**Recomendación para Benja:** un solo `<h1>` por página, visualmente el más grande, primero en el DOM visible, y **semánticamente alineado con el `<title>`** (misma keyword + zona, no necesariamente idéntico). H2 para secciones, H3 para sub-ítems, sin saltos H2→H4. No por "penalización", sino porque (a) reduce reescrituras de title, (b) le da a Google un título de reserva bueno, (c) accesibilidad.

---

## 2. Reescritura de titles y meta descriptions; largos óptimos 2026

### 2.1 Cuánto reescribe Google y por qué

| Estudio | Muestra | % title reescrito | Hallazgos clave | Etiqueta / URL / fecha |
|---|---|---|---|---|
| Zyppy (Cyrus Shepard) | 81.000 títulos | **61,6%** (cualquier cambio); ~40% en títulos de 51–60 caracteres | Títulos >60 car. se reescriben ~57–99% según largo; **títulos de 51–60 car. tienen la tasa más baja**; 84,87% de los títulos no tocados están en 50–60; Google **quita paréntesis 32% vs corchetes 77%**; separador **pipe "\|" se reescribe más que guion "-"**; títulos vacíos/duplicados/con keyword repetida se reescriben casi siempre; **H1 = title reduce reescritura** | [TEST] https://zyppy.com/seo/google-title-rewrite-study/ (2022, actualizado 2025) — citado vía `jacob-dietle/context-os` y `The-new-ben/justice-theme` (2026-06) |
| Mark McAlpin / Search Engine Land, Q1 2025 | miles de keywords YMYL y no-YMYL | **76,04%** | Google quita en promedio **2,71 palabras**, conserva sólo **35,02%** del title original; **en 63% de las reescrituras elimina el nombre de marca**; motivos: marca (63%), legibilidad (30%), alineación con intención | [TEST] https://searchengineland.com/google-changed-76-of-title-tags-in-q1-2025-heres-what-that-means-454847 (2025) |
| Ahrefs (Patrick Stox) | 953.276 páginas | 33,4% (2021) | Títulos >60 car. se reescriben 57% vs 39% los ≤60 | [TEST] [posiblemente desactualizado] https://ahrefs.com/blog/title-tag-rewrite/ (2021) |
| Google, blog oficial | — | — | Google explica por qué reescribe: *half-empty titles*, *obsolete titles*, *inaccurate titles*, *micro-boilerplate titles*, *boilerplate*, *keyword stuffing*, *no clear main title*; *"the title element is still by far the most-used source, more than 80% of the time"* | [OFICIAL] developers.google.com/search/blog/2021/09/more-info-about-titles (espejo `0xenzyme/awesome-seo-articles`, 2021) |

**Contradicción 61% vs 76%:** no son incompatibles: metodologías y años distintos (2022 vs 2025). La tendencia es **al alza**: cada vez más reescritura, sobre todo de marca y largo. Para Benja: asumir que **1 de cada 3 titles como mínimo, y probablemente 2 de cada 3, se van a ver distinto en la SERP**; el objetivo es que la parte que sobreviva (keyword + zona + gancho) sea la que importa.

### 2.2 Qué gatilla la reescritura (síntesis)

1. **Largo** (>60 caracteres / >600 px): el gatillo más fuerte y más documentado. [TEST] Zyppy, Ahrefs.
2. **Marca**: Google la quita o la mueve al final; 63% de las reescrituras 2025 la eliminan. [TEST] McAlpin.
3. **Keyword repetida / stuffing**: [OFICIAL] title-link doc: *"Avoid keyword stuffing… there's no reason to have the same words or phrases appear multiple times. Title text like 'Foobar, foo bar, foobars, foo bars' doesn't help the user, and this kind of keyword stuffing can make your results look spammy to Google and to users."*
4. **Boilerplate**: [OFICIAL] *"Long text in the `<title>` element that varies by only a single piece of information ('boilerplate' titles) is also bad."* → **Alerta directa para páginas servicio+zona generadas en serie.**
5. **Separadores**: pipe "|" se reescribe más que guion "-" [TEST] Zyppy; Google recomienda *"a delimiter such as a hyphen, colon, or pipe"* [OFICIAL].
6. **Mismatch title vs H1**: cuando difieren mucho, Google tiende a usar el H1 [TEST] Zyppy; cuando el title es "half-empty" Google va al H1 [OFICIAL].
7. **Emojis/símbolos**: ver punto 7.

### 2.3 Largo óptimo 2026

- **[OFICIAL]** Google: *"there's no limit on how long a `<title>` element can be, but the title link is truncated in Google Search results as needed, typically to fit the device width."* y para meta description: *"There's no limit on how long a meta description can be, but the snippet is truncated in Google Search results as needed, typically to fit the device width."* (doc snippet, actualización 2026-04 según el espejo `lesishu/seo-guide-skill/references/tkd-standard.md`).
- **[TEST]** Title: **50–60 caracteres ≈ 580–600 px desktop**; **móvil ≈ 496 px** (título que entra en desktop puede cortarse en móvil, aunque móvil muestra hasta 2 líneas). Análisis 2026 sobre 81.000 títulos (misma base Zyppy) mantiene 50–60 como *sweet spot*. — https://www.scalenut.com/blogs/meta-title-length-best-practices-2026 y https://titlelengthchecker.com/guides/ideal-title-tag-length-seo-guide.php (2026). Punto de corte típico observado: 525–535 px (https://theoceanmarketing.com/blog/title-tag-length-for-seo-best-practices/, 2026).
- **[TEST/OPINIÓN]** Meta description: **desktop ≈ 155–160 caracteres (~920 px)**, **móvil ≈ 120–130 caracteres**; lo que importa va en los **primeros 120 caracteres**. — https://www.devtoolcore.com/blog/meta-description-length-guide (2026), https://seoprog.com/guides/title-meta-length (2026).
- **[TEST]** Meta description reescrita: **Portent: 71% de las descripciones reescritas en página 1** (68% desktop / 71% móvil; Google usa la original ~30% del tiempo) — https://portent.com/blog/seo/how-often-google-ignores-our-meta-descriptions.htm (2020–2021; citado en HTTP Archive Web Almanac 2024 cap. SEO). **Seer Interactive abril 2025: 70% de las queries muestran descripción escrita por Google** — https://www.seerinteractive.com/insights/do-you-need-to-write-meta-descriptions-anymore-probably-not (2025). Otro estudio 2025: 63%. Rango consolidado **62–87% según query/dispositivo**.
- **[TEST]** HTTP Archive Web Almanac 2024: 98% de páginas tienen `<title>`, sólo **66,7% tienen meta description** — `HTTPArchive/almanac.httparchive.org/src/content/en/2024/seo.md` (2024).

**Recomendación para Benja:** title de **45–58 caracteres**, keyword+zona en los primeros 30, marca corta al final con guion (o sin marca en páginas servicio+zona si no entra); meta description de **120–150 caracteres**, primeros 120 con keyword+zona+beneficio+CTA. Asumir que la descripción se reescribe 2 de cada 3 veces → **el primer párrafo visible de la página tiene que funcionar también como snippet** (Google lo toma de ahí).

---

## 3. Leak 2024: `titlematchScore`, NavBoost y CTR

- **[FILTRACIÓN/PATENTE]** Origen: documentación interna del *Content Warehouse API* de Google publicada por error en GitHub entre marzo y mayo de 2024 (2.596 módulos, 14.014 atributos). Cobertura: https://searchengineland.com/google-search-document-leak-ranking-442617 (2024-05-28), iPullRank, SparkToro (Rand Fishkin).
- **[FILTRACIÓN/PATENTE]** **`titlematchScore`** vive en el módulo `QualityNsrNsrData` (señales NSR = calidad a nivel sitio). Descripción textual del atributo: *"Titlematch score of the site, a signal that tells how well titles are matching user queries."* Es **a nivel sitio**, no por página. — Espejo del leak `jroakes/Google-Data/keyAttributes.md` (2024) y mapa de evidencia `swan-gtm/gtm-skills/.../evidence-map.md` (2026). Implicación: **la coherencia entre títulos y queries se mide en todo el sitio**; un montón de páginas zona con titles boilerplate o desalineados baja el score de todo el dominio. **No hay medida de caracteres en el leak** (sólo un prefijo de snippet), o sea que "60 caracteres" es una convención de visualización, no del algoritmo.
- **[FILTRACIÓN/PATENTE]** **NavBoost / CRAPS** (`QualityNavboostCrapsCrapsClickSignals`, espejo hexdocs v0.4.0 en `jroakes/Google-Data/data/leak_content/`): campos `impressions`, `clicks`, `goodClicks`, `badClicks`, `lastLongestClicks`, `unicornClicks`, `unsquashedClicks`, `unsquashedImpressions`, `unsquashedLastLongestClicks`. Texto original del módulo: *"Click / impression signals for craps."* Los nombres están en el doc; la lectura "good = satisfactorio / bad = pogo-sticking / lastLongest = último clic largo de la sesión" es **interpretación de analistas** (iPullRank, SparkToro), no texto de Google. Ventana de **13 meses** de datos de clics; segmentación por país, dispositivo e idioma; Chrome como fuente de clickstream (`chromeInTotal`). El testimonio de Pandu Nayak en el juicio DOJ v. Google (2023) ya había confirmado NavBoost como uno de los sistemas más importantes. — https://www.seo-stack.io/blog/navboost-unpacked-what-the-google-content-warehouse-leak-actually-tells-us-about-click-based-ranking (2025), https://navboost.com/google-api-leak/ (2025).
- **[FILTRACIÓN/PATENTE]** Patente relacionada: US8938463B1 *"Modifying search result ranking based on implicit user feedback and a model of presentation bias"* (Google): el CTR se descuenta por posición (los primeros puestos reciben más clics por defecto), así que **lo que se aísla es la satisfacción post-clic**, no el CTR bruto.
- **[OFICIAL]** Google nunca reconoció públicamente que el CTR sea señal de ranking; Mueller e Illyes lo negaron en 2019–2020. Contradicción con el leak: **el leak muestra que los clics se almacenan y se usan en re-ranking (Twiddlers)**. Para Benja aplicar la versión del leak: escribir title/description que **fijen expectativas exactas** (zona, urgencia, precio si lo hay) para maximizar *goodClicks* y *lastLongestClicks*, y evitar ganchos engañosos que generen *badClicks*.

**Implicación práctica:** title y hero tienen que prometer lo mismo. Si el title dice "Cerrajero 24 hs Pocitos — Llegamos en 30 min" y el hero muestra un horario de 9 a 18, eso es un *badClick* que Google registra.

---

## 4. Dónde va keyword + zona y dónde van las variantes; stuffing vs cobertura semántica

### 4.1 Lo oficial sobre stuffing

- **[OFICIAL]** Spam policies (developers.google.com/search/docs/essentials/spam-policies, espejo `lesishu/seo-guide-skill/references-google/spampolicy-full.md`, 2026): *"Keyword stuffing refers to the practice of filling a web page with keywords or numbers in an attempt to manipulate rankings… Examples of keyword stuffing include: Lists of phone numbers without substantial added value · **Blocks of text that list cities and regions that a web page is trying to rank for** · Repeating the same words or phrases so often that it sounds unnatural."* → **El ejemplo de "bloques de ciudades y barrios" es literalmente el error clásico de sitios de servicios locales** (el footer con 60 barrios, el párrafo "cerrajero en Pocitos, cerrajero en Punta Carretas, cerrajero en Buceo…").
- **[OFICIAL]** Title-link doc: evitar repetir la misma frase en el title (ver 2.2).
- **[OFICIAL]** Guía de imágenes de Google (espejo `references-google/google-images.md`): alt descriptivo; el ejemplo "malo" de Google es explícitamente *"keyword stuffing"* en el alt.

### 4.2 Keyword en los primeros 100 palabras, alt, anchors internos

- **[OPINIÓN]** "Keyword en las primeras 100 palabras" es una regla de Backlinko/Brian Dean (2013→2025) sin confirmación de Google. Google nunca la afirmó; lo que sí dice es que el snippet se toma del contenido de la página (**[OFICIAL]** *"Google primarily uses the content on the page to automatically determine the appropriate snippet"*), lo que en la práctica **premia que el primer párrafo diga claramente servicio + zona** porque ese párrafo termina siendo el snippet cuando reescribe la description. Etiqueta: [OPINIÓN] con fundamento [OFICIAL] indirecto.
- **[OFICIAL]** Illyes (Reddit AMA, 2020, citado por Search Engine Roundtable): *"you can abuse your internal links as much as you want AFAIK"*; **no existe penalización por sobre-optimización de enlaces internos**. — https://www.seroundtable.com/google-no-internal-linking-overoptimization-penalty-27092.html (2019-2020) [posiblemente desactualizado].
- **[OFICIAL]** Mueller, abril 2025: ante la pregunta de si cuatro enlaces internos idénticos a la misma página diluyen el ranking: *"seems fine and common to me, I wouldn't worry about that"*. Resumen: Google dijo dos veces (2020 y 2025) que dejen de sobrepensar el anchor interno. — https://tamrank.com/blog/anchor-text-internal-links/ (2025), https://explodingtopics.com/blog/internal-linking (2025).
- **[FILTRACIÓN/PATENTE]** El leak tiene `anchorMismatchDemotion` y `phraseAnchorSpamPenalty` (módulos de spam de anchors); no distinguen explícitamente interno vs externo en la descripción disponible. Riesgo teórico si **todos** los anchors internos son exact match idénticos y el destino no coincide. — `ouranos-labs/pseolint/docs/superpowers/specs/2026-06-12-core-spambrain-gap-audit.md` (2026).
- **[TEST]** Ahrefs "Anchor text study" (https://ahrefs.com/blog/anchor-text-study, 2022–2024): correlación débil entre anchors exact-match y ranking; Penguin castigó exact match **externo** agresivo. [posiblemente desactualizado].

**Recomendación:** anchors internos descriptivos y variados ("cerrajero 24 hs en Pocitos", "servicio de cerrajería en Pocitos", "abrimos puertas en Pocitos"), sin miedo al exact match ocasional. Lo que no hay que hacer es la lista de 40 anchors "cerrajero + barrio" en el footer de todas las páginas: eso es "blocks of text that list cities" y además es *boilerplate*.

### 4.3 Mapa de ubicación (síntesis de todo lo anterior)

| Elemento | Va | No va | Respaldo |
|---|---|---|---|
| `<title>` | Keyword principal + zona, al inicio; 1 gancho (24 hs / precio / tiempo); marca corta al final o sin marca | Sinónimos en lista, repetir "cerrajero" dos veces, 3 barrios | [OFICIAL] title-link; [TEST] Zyppy |
| `<h1>` | Misma keyword + zona que el title, en frase natural | H1 distinto al title (gatilla reescritura) | [OFICIAL] blog 2021; [TEST] Zyppy |
| URL | `/cerrajero/pocitos/` o `/cerrajero-pocitos/`: keyword-zona, corta, sin stopwords | `/servicios/cerrajeria-urgente-24-horas-pocitos-montevideo-uruguay/` | [OPINIÓN] consenso; Google: "simple, descriptive" [OFICIAL] guía URL |
| Primer párrafo (≤ 60 palabras) | Servicio + zona + para quién + tiempo de llegada + CTA; es el snippet de reserva | Párrafo genérico "somos una empresa líder…" | [OFICIAL] snippet doc |
| H2 | Variantes de intención: "Apertura de puertas en Pocitos", "Cambio de cerraduras", "Cerrajero urgente de noche" | Repetir el H1 con otra preposición | [OPINIÓN] + cobertura semántica |
| H3 / FAQ | Long tail y jerga local: "¿Cuánto cobra un cerrajero en Pocitos?", "¿Llegan a Punta Carretas y Buceo?" | Preguntas inventadas sin respuesta real | [OPINIÓN] |
| Alt de imágenes | Qué se ve + contexto: "Cerrajero abriendo puerta blindada en edificio de Pocitos" | "cerrajero pocitos cerrajería pocitos 24hs" | [OFICIAL] guía imágenes |
| Anchors internos | Descriptivos, variados, 1–3 por página hacia la troncal y hacia zonas vecinas | Footer con 40 barrios | [OFICIAL] Illyes/Mueller; [OFICIAL] spam policy |
| Gentilicios / jerga ("cerrajería", "abrir la puerta", "me quedé afuera", "llave adentro", "de madrugada") | Cuerpo, H3, FAQ, testimonios | Title | [OPINIÓN] |
| "cerca de mí" / "cerca" | No en title/H1 (Google lo resuelve por geolocalización); sí una frase natural en cuerpo ("si buscás un cerrajero cerca en Pocitos…") | "Cerrajero cerca de mí Pocitos" como H1 | [OPINIÓN] consenso local SEO |

---

## 5. Fórmulas propuestas (title, description, H1, H2, H3, URL, alt, primer párrafo, anchors)

### 5.1 Patrones observados en sitios reales en español (HTML real, no ranking verificado)

No se pudo abrir la SERP (búsqueda bloqueada), así que en lugar de "top 5 que rankea" se extrajo el HTML real de sitios de cerrajeros/mudanzas/electricistas alojados en GitHub (España, Argentina, Uruguay, Colombia, Costa Rica, Alemania-es). **[OPINIÓN + datos observados]** — no prueban ranking, muestran qué patrones usa el mercado hispano en 2025–2026:

| Title real | Description real (recorte) | H1 real | Patrón |
|---|---|---|---|
| `Cerrajero Almería 24h \| Urgente · Llegamos en 20 Minutos \| 641 400 704` | "Cerrajero urgente en Almería disponible 24 horas. Apertura de puertas, cambio de cerraduras. Llegamos en 20 minutos. Sin sorpresas de precio. Llama ahora: 641 400 704." | — | KW+ciudad+24h+tiempo+teléfono (largo: 66 car., se corta) |
| `Cerrajero Urgente Almería 24h \| Llegamos en 20 Min · 641 400 704` (página troncal "urgente") | "…Llegamos en 15-20 minutos. Aperturas, cambios de cerradura y emergencias 24h/365. Llama ya…" | — | Troncal de servicio con modificador de intención |
| `Cerrajero en Berlín 24 horas desde 59 € \| Trust` | "Apertura sin daños… desde 59 €, llegada en 10–30 minutos y precio fijo por teléfono." | `Cerrajero en Berlín 24 horas – Apertura desde 59 €` | Precio en title y H1; H1 ≈ title |
| `Cerrajería Modelo Unión \| Servicio 24/7 Montevideo \| Urgencias` | "Cerrajería profesional 24/7 en Montevideo… Llegamos en 30 minutos. Hogar, comercio y automotriz." | — | Marca primero (peor: Google la mueve o quita) |
| `Cerrajería Jack Polara \| Cerrajero 24 hs en Córdoba Capital` | "…Cerrajero de urgencias 24 horas. Apertura de puertas sin romper, autos, cajas fuertes…" | — | Marca + KW + ciudad |
| `Cerrajeros de Urgencia en Valencia - Cerrajería Maestra` | — | `Cerrajeros de Urgencia en Valencia 24 horas` | H1 = title + "24 horas" |
| `Cerrajero Carkeys en General Rodríguez a Domicilio 24hs \| Autos y Hogar` | — | — | Página zona en carpeta `/buenos-aires/` |
| `Cerrajero Retiro`, `Cerrajero Arganzuela` (carpeta `/zonas/`) | — | — | Título ultracorto (half-empty → Google lo va a completar con el H1) |
| `Mudanzas en Junín Mendoza \| Traslados Seguros y Rápidos \| Mudanzas Miranda` | "Servicio de mudanzas y traslados en Junín, Mendoza… ¡Escribinos por WhatsApp!" | — | Páginas zona bajo `/mudanzas-mendoza/mudanzas-junin.html`; **CTA WhatsApp en la description** |
| `Electricista en Capital Federal` / `Electricista Cerca 24hs.` / `Electricista Matriculado los 365 dias, 24hs.` (electricista24horas.com.ar) | "…electricista autorizado por COPIME y CTPBA. Atención rápida y segura en todo CABA." | — | Matrícula/credencial como gancho en description (CABA) |
| `<h1>Cerrajero en Triana</h1>` + párrafo con sub-barrios ("calle Betis, San Jacinto, Barrio León…") | — | — | Sub-zonas en el primer párrafo, no en el H1 |

**Patrones dominantes en el mercado hispano (2025–2026):** (1) `Servicio + [en] + Zona` al inicio; (2) modificador "24 hs / 24 horas / urgente"; (3) gancho concreto "llegamos en X min" o "desde $X"; (4) teléfono en title (España; se corta en móvil y Google suele quitarlo); (5) marca al final con "|" o "-"; (6) en Argentina/Uruguay se usa "24 hs" y "a domicilio"; "matriculado" en electricistas CABA; (7) description con CTA imperativo ("Llamá", "Escribinos por WhatsApp").

### 5.2 Fórmulas por tipo de página

#### (a) HOME (marca + categoría + ciudad)

| Elemento | Fórmula | Ejemplo cerrajería Montevideo | Ejemplo mudanzas CABA |
|---|---|---|---|
| `<title>` (≤ 58 car.) | `[Servicio] en [Ciudad] 24 hs \| [Gancho corto] – [Marca]` | `Cerrajero en Montevideo 24 hs \| Llegamos en 30 min – Llave Ya` (57) | `Mudanzas en CABA \| Presupuesto por WhatsApp – MudaFácil` (54) |
| Meta description (120–150) | `[Servicio] [modificador] en [Ciudad] y [zonas top 2–3]. [Beneficio concreto]. [Prueba]. [CTA WhatsApp].` | `Cerrajero 24 hs en Montevideo: Pocitos, Centro, Carrasco. Apertura sin romper la puerta, llegamos en 30 min. +500 aperturas. Escribinos por WhatsApp.` (148) | `Mudanzas en CABA y GBA con embalaje incluido. Presupuesto cerrado en 10 min por WhatsApp, sin sorpresas. Camiones propios y personal asegurado.` (144) |
| `<h1>` | `[Servicio] en [Ciudad] 24 hs: [promesa]` | `Cerrajero en Montevideo 24 hs: llegamos en 30 minutos` | `Mudanzas en CABA con presupuesto cerrado por WhatsApp` |
| H2 (orden) | Servicios (uno por troncal) · Zonas · Cómo trabajamos · Precios orientativos · Opiniones · FAQ · Contacto | `Nuestros servicios de cerrajería` / `Zonas de Montevideo donde llegamos` / `Cómo trabajamos` / `Precios de cerrajería en Montevideo` / `Opiniones de clientes` / `Preguntas frecuentes` | ídem |
| H3 | Un H3 por troncal bajo el H2 "servicios", con anchor a la troncal | `Apertura de puertas` → `/apertura-de-puertas/` | `Mudanzas de departamentos` → `/mudanzas-departamentos/` |
| URL | `/` | `/` | `/` |
| Alt hero | `[Profesional] de [Marca] [acción] en [Ciudad]` | `Cerrajero de Llave Ya abriendo una puerta en Montevideo` | `Camión de MudaFácil cargando una mudanza en Palermo, CABA` |
| Primer párrafo (≤ 50 palabras) | Qué + dónde + cuándo + cuánto tarda + CTA | `Somos cerrajeros en Montevideo con atención las 24 horas. Abrimos puertas sin romper la cerradura, cambiamos cerraduras y hacemos copias de llaves a domicilio. Llegamos en 30 minutos a Pocitos, Centro y Carrasco. Escribinos por WhatsApp y te decimos el precio antes de salir.` | análogo |
| Anchors internos salientes | Nombre natural del servicio; hacia zonas: "cerrajero en Pocitos" | `apertura de puertas`, `cerrajero en Pocitos`, `cerrajero en Carrasco` | `mudanzas en Palermo`, `mudanzas en Caballito` |

#### (b) TRONCAL DE SERVICIO (servicio + ciudad)

| Elemento | Fórmula | Ejemplo electricista Ciudad de la Costa | Ejemplo yeso Caballito (CABA) |
|---|---|---|---|
| `<title>` | `[Servicio específico] en [Ciudad] \| [Gancho] – [Marca]` | `Electricista en Ciudad de la Costa 24 hs \| Urgencias y UTE – Volt` (60 → recortar marca si hace falta) | `Yesero en Caballito \| Cielorrasos y molduras – Yeso Total` (54) |
| Meta description | `[Servicio] en [Ciudad] para [problemas 2–3]. [Credencial]. [Tiempo]. [CTA WhatsApp].` | `Electricista matriculado en Ciudad de la Costa: cortes de luz, tableros, trámites UTE. Atendemos urgencias 24 hs, llegamos en 40 min. Pedí presupuesto por WhatsApp.` (150) | `Yesería en Caballito: cielorrasos, molduras, reparación de humedad. Presupuesto sin cargo en 24 hs, trabajos con garantía. Escribinos por WhatsApp.` (139) |
| `<h1>` | `[Servicio] en [Ciudad]: [promesa]` | `Electricista en Ciudad de la Costa: urgencias 24 hs y trámites UTE` | `Yesero en Caballito: cielorrasos, molduras y arreglos con garantía` |
| H2 | Qué hacemos (sub-servicios) · Cuándo llamarnos (síntomas) · Precios · Zonas que cubrimos · Proceso · Opiniones · FAQ | `Trabajos eléctricos que hacemos` / `Señales de que necesitás un electricista` / `Precios de electricista en Ciudad de la Costa` / `Barrios de Ciudad de la Costa donde llegamos` | análogo |
| H3 | Sub-servicios (cada uno puede ser futura página) y una H3 por zona con anchor a la página servicio+zona | `Cambio de tablero` / `Electricista en Solymar` (→ `/electricista/solymar/`) | `Cielorraso de yeso` / `Yesero en Caballito Norte` |
| URL | `/[servicio]/` o `/[servicio]-[ciudad]/` si la ciudad no está en el dominio | `/electricista-ciudad-de-la-costa/` | `/yeso-caballito/` |
| Alt | `[Acción concreta] en [tipo de inmueble] de [Ciudad]` | `Electricista cambiando un tablero en una casa de Ciudad de la Costa` | `Yesero aplicando molduras en un living de Caballito` |
| Primer párrafo | Servicio + ciudad + 3 problemas + credencial + tiempo + CTA | `Si te quedaste sin luz o saltó la térmica en Ciudad de la Costa, somos electricistas matriculados con atención las 24 horas. Reparamos tableros, hacemos instalaciones nuevas y gestionamos trámites con UTE. Llegamos en 40 minutos a Solymar, Lagomar y El Pinar. Escribinos por WhatsApp.` | análogo |
| Anchors | Hacia home (marca), hacia zonas hijas (H3), hacia troncales hermanas | `electricista en Solymar`, `instalaciones eléctricas` | `yesero en Flores`, `reparación de humedad en paredes` |

#### (c) SERVICIO + ZONA (barrio / localidad)

| Elemento | Fórmula | Ejemplo cerrajero Pocitos | Ejemplo mudanzas Palermo (CABA) |
|---|---|---|---|
| `<title>` (sin marca si no entra) | `[Servicio] en [Zona] 24 hs \| [Gancho local]` | `Cerrajero en Pocitos 24 hs \| Llegamos en 20 min` (47) | `Mudanzas en Palermo \| Presupuesto por WhatsApp hoy` (49) |
| Meta description | `[Servicio] en [Zona], [Ciudad]. [Beneficio]. [Referencia local]. [CTA].` | `Cerrajero 24 hs en Pocitos, Montevideo. Apertura de puertas sin daños, cambio de cerraduras y llaves. Estamos a 20 min de la rambla y Bulevar España. Escribinos por WhatsApp.` (154 → recortar a 150) | `Mudanzas en Palermo, CABA: Soho, Hollywood y Chico. Embalaje, flete y armado de muebles. Conocemos las restricciones de estacionamiento del barrio. Pedí precio por WhatsApp.` (150) |
| `<h1>` | `[Servicio] en [Zona]: [promesa local]` | `Cerrajero en Pocitos: llegamos en 20 minutos, las 24 horas` | `Mudanzas en Palermo con presupuesto cerrado por WhatsApp` |
| H2 (orden) | Servicios en la zona · Por qué elegirnos en [Zona] (prueba local) · Precios · Sub-zonas/referencias · Proceso · FAQ local · Otras zonas cercanas | `Servicios de cerrajería en Pocitos` / `Trabajos recientes en Pocitos` / `Precios en Pocitos` / `Llegamos a Pocitos Nuevo, Villa Biarritz y Punta Carretas` / `Preguntas frecuentes de vecinos de Pocitos` | análogo con Palermo Soho / Hollywood / Chico / Botánico |
| H3 | Sub-servicio + zona sólo en 1–2 H3 (no en todos); resto sin zona | `Apertura de puertas en Pocitos` / `Cambio de cerraduras` / `Cerrajero de noche` | `Mudanzas de monoambientes` / `Mudanzas de oficinas en Palermo` |
| URL | `/[servicio]/[zona]/` (jerarquía) o `/[servicio]-[zona]/` (plana) — elegir una y no mezclar | `/cerrajero/pocitos/` | `/mudanzas/palermo/` |
| Alt | Prueba local visible | `Cerrajero abriendo la puerta de un apartamento en Pocitos, Montevideo` | `Camión de mudanzas estacionado en Palermo Soho` |
| Primer párrafo (el más importante: es el snippet de reserva y la señal anti-boilerplate) | Debe contener algo **que sólo aplique a esa zona**: referencia geográfica, tipo de vivienda, problema típico, tiempo de llegada desde la base | `Si te quedaste afuera en Pocitos, llegamos en 20 minutos: nuestra base está en Bulevar España y 26 de Marzo. Trabajamos con las cerraduras de los edificios de la rambla y con puertas blindadas. Abrimos sin romper y te pasamos el precio por WhatsApp antes de salir.` | `Hacemos mudanzas en Palermo todos los días. Conocemos los horarios de carga y descarga de Soho y Hollywood, los edificios sin ascensor de Palermo Viejo y los pasillos angostos de los PH. Presupuesto cerrado por WhatsApp en 10 minutos.` |
| Anchors internos | 1 hacia la troncal ("cerrajero en Montevideo"), 2–4 hacia zonas vecinas, 1 hacia home | `cerrajero en Punta Carretas`, `cerrajero en Buceo`, `cerrajería en Montevideo` | `mudanzas en Villa Crespo`, `mudanzas en Belgrano`, `mudanzas en CABA` |
| Schema | `LocalBusiness` (o subtipo `Locksmith`, `MovingCompany`, `Electrician`) + `areaServed` + `Service`; **sin** `aggregateRating` propio (ver punto 8) | — | — |

**Regla anti-boilerplate para (c):** si al reemplazar "Pocitos" por "Buceo" la página queda igual, Google la va a tratar como boilerplate (title) y contenido duplicado/thin (cuerpo). Mínimo 30–40% del texto tiene que ser específico de la zona: referencias, fotos, testimonios con barrio, precios si varían, FAQ local.

---

## 6. Orden ideal de secciones de una página de servicio local que rankea y convierte

### 6.1 Datos de conversión (no opinión)

- **[TEST]** Nielsen Norman Group, eyetracking 2018 (120 participantes, >130.000 fijaciones): **57% del tiempo de visualización ocurre above the fold; 74% en las dos primeras pantallas** (bajó de 80% en 2010: la gente scrollea más, pero el primer viewport sigue siendo el que manda). — https://www.nngroup.com/articles/scrolling-and-attention/ (2018) [posiblemente desactualizado, pero es el dato más citado y NN/g no lo reemplazó].
- **[TEST]** Unbounce Conversion Benchmark Report: **mediana general 6,6%** (edición 2024, 464 M de visitas; 41.000 landing pages); rango por industria 3,8% (SaaS) a 12,3% (legal); la edición 2025 reporta media 5,89%. — https://unbounce.com/conversion-benchmark-report/ y https://unbounce.com/average-conversion-rates-landing-pages/ (2024–2025). No se pudo leer la fila "Home improvement/Home services" [no verificado en esta sesión]; una cita secundaria de la edición 2026 en un manual PPC da **Home Improvement: CTR 4,80% / conversión 10,22%** para Google Ads (`Draivix/aidvertaiser`, 2026) — tomar con pinzas.
- **[TEST]** Unbounce 2024 (57 M de conversiones): páginas con **nivel de lectura de 5.º–7.º grado convierten 11,1% vs 5,3% las de nivel "profesional"**. — citado en `alexwox/genesis-template` (2026) desde el benchmark 2024. → Escribí simple, frases cortas, sin jerga técnica.
- **[TEST]** Google/Ipsos, "Click to call research" (thinkwithgoogle.com/_qs/documents/690/click-to-call_research-studies.pdf): **70% de los que buscan desde el móvil usaron click-to-call**; 61% dice que la llamada importa sobre todo en la fase de compra; +8% CTR en anuncios con botón de llamada. (2013) [posiblemente desactualizado; el equivalente 2026 en Uruguay/Argentina es click-to-WhatsApp].
- **[TEST]** KoMarketing (2024): sitios con teléfono visible convierten **54% más leads** que los que esconden el contacto. — citado en https://www.verlua.com/blog/website-trust-signals-convert-visitors (2025) [fuente secundaria].
- **[TEST]** Chartbeat (2 mil millones de visitas): **71% de los usuarios scrollea**; 29% nunca lo hace. — citado en `nickzsche21/waterline` (2026).
- **[TEST]** Prueba social: quitar testimonios bajó la conversión ~35% en un caso de Michael Aagaard (ContentVerve); CTA en primera persona ("Quiero mi presupuesto") +90% replicado 3 veces (ContentVerve). — `Eneryleen/ai-web-design-codex` y `alexwox/genesis-template` (2026) [posiblemente desactualizado: casos 2012–2015].
- **[TEST]** Baymard: ~18% de los usuarios busca explícitamente indicadores de seguridad/confianza antes de dar datos; sellos cerca del formulario/CTA suben conversión 5–15% en marcas desconocidas. — https://baymard.com/blog/site-seal-trust (2023) [e-commerce, extrapolación].
- **[TEST]** Trustpilot "Value of Ratings and Reviews" (2023): mostrar el **conteo** de reseñas junto a la estrella sube conversión 28–33%. — PDF citado en `Aetheria-Labs1/storefront-skills` (2026).
- **[OPINIÓN + datos secundarios]** WhatsApp como CTA: no se encontró un estudio controlado publicado sobre "botón WhatsApp vs formulario" en servicios locales; Meta publica casos con "+X% leads" pero son casos de anuncios click-to-WhatsApp, no de landing orgánica. **Vacío de evidencia**: Benja debería medirlo él mismo con `click_wsp` (esto lo convierte en dueño de un dato que el mercado no tiene).

### 6.2 Orden recomendado (servicio + zona y troncal), con justificación

| # | Sección | Qué contiene | Por qué en ese lugar |
|---|---|---|---|
| 1 | **Hero** (viewport 1, móvil primero) | H1 · subtítulo con tiempo de llegada/precio desde · **botón WhatsApp grande** + botón llamar · 1 línea de prueba (★ 4,9 · 312 reseñas Google · "matriculado") · foto real | 57% del tiempo de atención está acá (NN/g); 29% no scrollea (Chartbeat); teléfono visible +54% leads |
| 2 | **Barra de confianza** | Años, cantidad de trabajos, garantía, matrícula/BPS/DGI si aplica, "sin cargo por visita" | Trust cerca del CTA (Baymard); reduce fricción sin scroll |
| 3 | **Servicios en esta zona** (H2 + H3 con anchors) | 3–6 tarjetas con precio "desde" | Cubre intención informacional/comercial; alimenta interlinking |
| 4 | **Prueba social local** (H2) | 3 reseñas con barrio y nombre, fotos de trabajos, mapa de zonas | Quitar testimonios −35%; reseñas con conteo +28–33% |
| 5 | **Cómo trabajamos / proceso** (H2, 3–4 pasos) | "Escribís por WhatsApp → te pasamos precio → llegamos en 20 min → pagás al terminar" | Fija expectativas → *goodClicks* (leak) y menos abandono |
| 6 | **Precios orientativos** (H2, tabla) | Rangos honestos, qué incluye, formas de pago | La query "cuánto cobra un cerrajero" es informacional-comercial; tabla = snippet-able |
| 7 | **Zona y cobertura** (H2) | Sub-barrios, referencias, tiempo de llegada por sub-zona, mapa | Especificidad anti-boilerplate; NO lista de 40 barrios |
| 8 | **FAQ local** (H2 + H3 preguntas) | 4–6 preguntas reales de clientes de la zona | Long tail; sin rich result desde mayo 2026 (ver punto 8), pero sí contenido citable por AI Overviews/AI Mode |
| 9 | **CTA final + sticky** | Repetir botón WhatsApp; **botón fijo abajo en móvil** durante todo el scroll | "Kept stuck to the top or bottom of the screen as they scroll" (The Ad Firm 2025); segundo CTA para el 71% que scrollea |
| 10 | **Enlaces a zonas vecinas + troncal** | 3–5 anchors descriptivos | Interlinking sin footer-spam |

Home: mismo orden pero (3) son las troncales, (7) es la lista de zonas con anchors (máx. ~10–15 visibles, resto en página "zonas").

---

## 7. Meta description: teléfono, precio, CTA, emojis y símbolos

- **[OFICIAL]** Google sobre meta descriptions: *"They are like a pitch that convince the user that the page is exactly what they're looking for."* y las usa *"if we think it gives users a more accurate description than would be possible purely from the on-page content."* (doc snippet, 2026). No prohíbe teléfono ni precio; sí desaconseja listas de keywords y texto genérico.
- **[TEST]** Moz: descripciones con propuesta de valor clara suben CTR hasta **5,8%** vs sin description — citado en https://www.seo-day.de/wiki/on-page-seo/html-optimierung/meta-descriptions/cta-descriptions?lang=en (2025) [fuente secundaria, estudio no fechado].
- **[TEST]** Ritner Digital (2025): CTA en la description ayuda **cuando está en los primeros 120 caracteres y es específica** ("Presupuesto en 10 min por WhatsApp"), no el genérico "¡Contactanos!". — https://www.ritnerdigital.com/blog/should-you-put-a-cta-at-the-end-of-every-meta-description-heres-what-the-data-actually-says (2025).
- **[OPINIÓN]** Teléfono en la description (https://theaustineditor.com/phone-numbers-meta-descriptions/): puede generar "zero-click" (llaman sin entrar) → para Benja eso es **bueno** si la llamada se atribuye (usar número de seguimiento) pero **malo para medir `click_wsp`** y para NavBoost (no hay clic → no hay *goodClick*). Recomendación: **sin teléfono en la description; sí "por WhatsApp" como CTA verbal**. Precio "desde" sí, si es real y estable (sube CTR cualificado y baja *badClicks*).
- **Emojis y símbolos:**
  - **[OFICIAL]** Mueller (varias veces 2018–2024): Google **puede** mostrar emojis en titles/descriptions pero los **filtra** cuando los considera engañosos, irrelevantes o cuando rompen la legibilidad; no dan ranking. — https://mangools.com/blog/seo-emojis/ (2025), https://bloggerpilot.com/en/seo-emoji/ (2026).
  - **[TEST]** SearchPilot, emoji en title tags (https://www.searchpilot.com/resources/case-studies/seo-testing-lessons-emoji-title-tags): **resultado negativo/inconcluso**: *"Google was rewriting the titles to remove both the element we thought would attract more clicks (the emoji), and the main keyword."* → el emoji gatilló reescritura y se perdió la keyword. Test hermano con emoji en meta descriptions (https://www.searchpilot.com/resources/case-studies/seo-split-test-lessons-emoji-meta-descriptions/) [resultado no leído en esta sesión].
  - **[TEST]** Casos positivos puntuales: emoji de cóctel en página de cócteles +11% CTR; hamburguesa +3% (Bitvero, Genie Crawl 2024–2025) — nicho/relevancia extrema.
  - **[OPINIÓN]** Símbolos tipográficos (·, –, ✓, ★, →) suelen sobrevivir mejor que emojis Unicode de color; el "★ 4,9" en description funciona sólo si Google no lo filtra (inconsistente).

**Recomendación:** sin emojis en title (riesgo de reescritura + pérdida de keyword). En description, como mucho un "✓" o "★ 4,9 (312 reseñas)" y medir CTR en Search Console 4 semanas; si Google lo reescribe, sacarlo. Sin teléfono en description. Precio "desde" sí. CTA "por WhatsApp" sí, dentro de los primeros 120 caracteres.

---

## 8. Rich results que todavía se muestran en 2026 para páginas de servicio

| Rich result | Estado sept. 2026 | Fuente |
|---|---|---|
| **FAQ** (`FAQPage`) | **Muerto para todos.** Ago-2023: restringido a *"well-known, authoritative government and health websites"* [OFICIAL, blog 2023-08-08 "Changes to HowTo and FAQ rich results"]. **7 de mayo de 2026: retirado para todos los sitios.** Nota textual agregada al doc FAQPage (2026-05-08): *"As of May 7, 2026, FAQ rich results are no longer appearing in Google Search. We will be dropping the FAQ search appearance, rich result report, and support in the Rich results test in June 2026."* Soporte en la API de Search Console se retira en agosto 2026. Google dice que pueden dejar el markup (otros buscadores lo usan). Docs FAQPage removidos 2026-06-15. | [OFICIAL] developers.google.com/search/updates#removing-faq-rich-result (citado textualmente en `frank890417/taiwan-md/reports/seo-optimization-plan-2026-06-07.md` y `johnkorzhuk/grabient/seo-research/indexing-and-ai-visibility.md`); https://searchengineland.com/google-to-no-longer-support-faq-rich-results-476957 (2026-05); https://www.searchenginejournal.com/google-drops-faq-rich-results-from-search/574429/ (2026-05) |
| **HowTo** | Eliminado en móvil ago-2023 y en desktop **13/14 de septiembre de 2023**; docs removidos. | [OFICIAL] blog 2023-08 + changelog 2023-09-14 |
| **Sitelinks search box** | Retirado globalmente 21-nov-2024; markup inofensivo. | [OFICIAL] developers.google.com/search/blog/2024/10/sitelinks-search-box |
| **7 tipos retirados jun-2025** | Book Actions, Course Info, Claim Review, Estimated Salary, Learning Video, Special Announcement, Vehicle Listing (anuncio Henry Hsu 2025-06-12; reportes y Rich Results Test los quitan desde 2025-09-08). Practice Problems: aviso 2025-06-12, docs removidos 2026-01-06. Ninguno afecta a Benja. | [OFICIAL] developers.google.com/search/updates; https://www.seroundtable.com/google-drops-support-structured-data-types-40386.html (2025-06) |
| **Review snippet / estrellas para LocalBusiness** | **No elegible si las reseñas son "self-serving"** (la entidad controla las reseñas sobre sí misma, incluidos widgets embebidos de Google/Facebook). Regla desde sept-2019, **reafirmada en la actualización del doc del 10-dic-2025**: *"If the entity that's being reviewed controls the reviews about itself, their pages that use LocalBusiness or any other type of Organization structured data are ineligible for star review feature."* Además, agregar `aggregateRating` con reseñas copiadas de Google viola los ToS y puede traer acción manual. | [OFICIAL] developers.google.com/search/docs/appearance/structured-data/review-snippet (2025-12-10); developers.google.com/search/blog/2019/09/making-review-rich-results-more-helpful; https://www.brightlocal.com/learn/review-schema/ (2025) |
| **Breadcrumb** | Sigue vigente y es lo más barato: reemplaza la URL en la SERP desktop. En 2025 Google simplificó la visualización en **móvil** (muestra sólo el nombre de sitio/dominio en muchos casos) [no verificado en esta sesión; posiblemente desactualizado]. Igual conviene el markup: desambigua jerarquía `Cerrajería › Montevideo › Pocitos`. | [OFICIAL] developers.google.com/search/docs/appearance/structured-data/breadcrumb; [OPINIÓN] `clawic/skills/skills/seo/schema.md` (2026): "Breadcrumb: Active… cheap and universal" |
| **Sitelinks** (orgánicos, para búsquedas de marca) | Vigentes; se generan solos con buena arquitectura, títulos claros y anchors internos descriptivos. No hay markup. | [OFICIAL] developers.google.com/search/docs/appearance/sitelinks |
| **LocalBusiness** (`Locksmith`, `MovingCompany`, `Electrician`, `HVACBusiness`, `GeneralContractor`) | Vigente: nombre, dirección, teléfono, horarios, `areaServed`, `geo`, `priceRange`, `sameAs` (GBP, Instagram). No genera un rich result visual por sí solo en la SERP web (alimenta el Knowledge Panel / entidad), pero es la base de coherencia NAP con Google Business Profile. | [OFICIAL] developers.google.com/search/docs/appearance/structured-data/local-business |
| **Site name** | Vigente: `WebSite` + `name` para que la SERP muestre el nombre de marca, no el dominio. | [OFICIAL] developers.google.com/search/docs/appearance/site-names |
| **Imágenes / Video** | Vigentes; fotos reales con alt + `ImageObject` opcional; video sólo si hay. | [OFICIAL] |

**Conclusión punto 8:** para páginas de servicio local en 2026 quedan **Breadcrumb, LocalBusiness/Service, Site name, y (indirectamente) Sitelinks**. FAQ y HowTo no dan nada visual; estrellas propias no son elegibles. La FAQ sigue valiendo como **contenido** (long tail + citas en AI Overviews/AI Mode: Google afirma que no hace falta schema especial para AI Overviews), no como schema.

---

## Fórmulas propuestas — resumen en una tabla (para copiar al skill)

| Página | Title | H1 | URL | Description (primeros 120 car.) |
|---|---|---|---|---|
| Home | `[Servicio] en [Ciudad] 24 hs \| [Gancho] – [Marca]` | `[Servicio] en [Ciudad] 24 hs: [promesa]` | `/` | `[Servicio] [mod.] en [Ciudad]: [zonas]. [Beneficio]. [Prueba]. Escribinos por WhatsApp.` |
| Troncal | `[Servicio específico] en [Ciudad] \| [Gancho] – [Marca]` | `[Servicio específico] en [Ciudad]: [promesa]` | `/[servicio]/` | `[Servicio] en [Ciudad] para [3 problemas]. [Credencial]. [Tiempo]. Pedí precio por WhatsApp.` |
| Servicio+zona | `[Servicio] en [Zona] 24 hs \| [Gancho local]` | `[Servicio] en [Zona]: [promesa local]` | `/[servicio]/[zona]/` | `[Servicio] en [Zona], [Ciudad]. [Beneficio]. [Referencia local]. Escribinos por WhatsApp.` |

Ejemplos completos: **cerrajero Pocitos** (5.2c), **mudanzas Palermo CABA** (5.2c), **electricista Ciudad de la Costa** (5.2b), **yeso Caballito** (5.2b).

---

## Implicancias para Benja

1. **Un H1 por página, alineado con el title.** No porque Google lo exija (no lo hace: "as many as you want"), sino porque reduce reescrituras de title (Zyppy), le da a Google un título de reserva bueno (blog 2021) y porque `titlematchScore` es a nivel sitio (leak): la coherencia se mide en todo el dominio.
2. **Asumir reescritura: 61–76% de titles y 63–71% de descriptions.** Escribir para que lo que sobreviva sea keyword + zona + gancho, en los primeros 30 caracteres del title y los primeros 120 de la description. Sin marca al inicio (Google la quita en 63% de las reescrituras).
3. **El primer párrafo es el snippet real.** Google toma el snippet del contenido "primarily"; en páginas zona tiene que llevar servicio + zona + referencia local + tiempo + CTA WhatsApp en ≤ 60 palabras.
4. **Boilerplate = el riesgo #1 del modelo servicio+zona.** Google lo nombra explícitamente tanto en title-link ("boilerplate titles") como en spam policies ("blocks of text that list cities and regions"). Cada página zona necesita 30–40% de contenido único y verificable (referencias, fotos, reseñas con barrio, precios si varían). Nada de footers con 40 barrios.
5. **Anchors internos: descriptivos y variados, sin paranoia por exact match.** Illyes 2020 y Mueller 2025 lo dijeron; el único riesgo real es el patrón de lista masiva.
6. **Title y hero deben prometer lo mismo** (NavBoost: goodClicks vs badClicks). "Llegamos en 20 min" en el title implica un hero que lo repita y un negocio que lo cumpla.
7. **Orden de secciones:** hero con H1 + WhatsApp + prueba (57% de la atención está ahí) → barra de confianza → servicios → reseñas locales → proceso → precios → zona → FAQ → CTA final + botón WhatsApp sticky en móvil. Nivel de lectura simple (11,1% vs 5,3% de conversión, Unbounce 2024).
8. **Meta description:** precio "desde" sí; CTA "por WhatsApp" sí (primeros 120 car.); teléfono no (mata el clic y la medición); emojis no en title, opcional y medido en description.
9. **Schema en 2026:** Breadcrumb + LocalBusiness (subtipo) + Service + WebSite/site name. FAQPage puede quedar pero no rinde nada visual desde el 7-may-2026; `aggregateRating` propio **no** (inelegible + riesgo de acción manual). Mostrar reseñas y conteo como texto visible sí (+28–33% conversión según Trustpilot).
10. **Medir lo que el mercado no mide:** no hay estudio publicado de "botón WhatsApp vs formulario" en servicios locales rioplatenses. Con `click_wsp` por página y por posición del botón (hero / sticky / final), Benja puede tener en 8 semanas un dato propio que vale más que cualquier benchmark de acá.
11. **Checklist técnico de largo:** title 45–58 car. (≤ 580 px), description 120–150 car., H1 ≤ 70 car., URL ≤ 3 niveles y sin stopwords, alt 8–15 palabras descriptivas.

---

## Contradicciones encontradas

| Tema | Postura A | Postura B | Qué aplicar para Benja |
|---|---|---|---|
| Múltiples H1 | [OFICIAL] Mueller: "as many as you want", sin límite ni penalización | [OPINIÓN] herramientas SEO y accesibilidad (BOIA, Screaming Frog Warning): un solo H1 | **Un solo H1.** Coincide con la doc de title-link ("main title distintivo, first visible h1") y evita reescrituras. |
| % de reescritura de titles | [TEST] Zyppy 61% (2022) / Ahrefs 33% (2021) | [TEST] McAlpin/SEL 76% (Q1 2025) | Planificar con el escenario alto (76%): lo importante en los primeros 30 caracteres. |
| Title = H1 | [TEST] Zyppy: igualarlos reduce reescritura | [OPINIÓN] dev.to y otros: que sean distintos para cubrir más keywords | **Semánticamente iguales, no idénticos**: mismo servicio + zona; el H1 puede sumar la promesa. |
| CTR como factor de ranking | [OFICIAL] Google lo niega (2019–2020) | [FILTRACIÓN] NavBoost almacena y usa clics 13 meses; testimonio DOJ | Actuar como si contara: expectativa exacta en title/description, cumplimiento en hero. |
| Exact-match en anchors internos | [OFICIAL] Illyes/Mueller: sin penalización, "no se preocupen" | [OPINIÓN] consenso post-Penguin: 1–5% exact match; [FILTRACIÓN] `anchorMismatchDemotion` | Variar por naturalidad y UX; exact match ocasional sin miedo; prohibido el footer-lista. |
| Teléfono en meta description | [OPINIÓN] sube contactos directos (zero-click útil) | [OPINIÓN/FILTRACIÓN] mata el clic → no hay `click_wsp` ni goodClick | Sin teléfono en description; WhatsApp como CTA verbal. |
| Emojis en title | [TEST] casos +3% a +11% CTR en nichos | [TEST] SearchPilot: Google reescribió y borró emoji + keyword | Sin emojis en title; test controlado sólo en description. |
| FAQ schema | [OPINIÓN] "dejalo, sirve para AI/Bing" | [OFICIAL] sin rich result para nadie desde 2026-05-07; Google: no hace falta schema para AI Overviews | Dejarlo si ya está (inofensivo), no invertir tiempo; invertir en la FAQ como contenido visible. |
| Estrellas para negocios locales | Plugins/consultores que las prometen | [OFICIAL] self-serving = inelegible (2019, reafirmado 2025-12-10) | No usar `aggregateRating` propio; mostrar reseñas como texto y linkear a GBP. |
| "Keyword en las primeras 100 palabras" | [OPINIÓN] Backlinko | Sin respaldo oficial; lo oficial es que el snippet sale del contenido | Aplicar por la razón correcta: primer párrafo = snippet de reserva. |
| Largo del title en caracteres | [OPINIÓN] "60 caracteres" como regla | [OFICIAL] "no hay límite, se trunca por ancho"; [FILTRACIÓN] no hay medida de caracteres en el leak | Medir en píxeles (≤ 580 px), pensar móvil (≈ 496 px, 2 líneas). |
| Unbounce home services | Búsqueda: no aparece el dato de la vertical | Cita secundaria 2026: 10,22% (Ads) | No usar como benchmark; usar `click_wsp` propio. |

---

### Fuentes primarias efectivamente consultadas (por vía de espejo GitHub, por bloqueo del proxy)

1. Google Search Central — Title links (`lesishu/seo-guide-skill/references-google/title-link.md`, 2026) [OFICIAL]
2. Google Search Central — Snippets / meta description (`…/snippet.md`, act. 2026-04) [OFICIAL]
3. Google Search Central — Spam policies, keyword stuffing (`…/spampolicy-full.md`, 2026) [OFICIAL]
4. Google Search Central Blog — "More info about titles" (sept-2021) (`0xenzyme/awesome-seo-articles`) [OFICIAL]
5. Nota oficial de retiro de FAQ rich results (doc FAQPage, 2026-05-08, cita textual en `frank890417/taiwan-md` y changelog en `johnkorzhuk/grabient`) [OFICIAL]
6. Leak 2024 — `QualityNavboostCrapsCrapsClickSignals` (espejo hexdocs v0.4.0 en `jroakes/Google-Data`) y `titlematchScore` (`QualityNsrNsrData`, `jroakes/Google-Data/keyAttributes.md`) [FILTRACIÓN]
7. HTTP Archive Web Almanac 2024, capítulo SEO (`HTTPArchive/almanac.httparchive.org`) [TEST]
8. Review snippet guidelines — cita textual de la regla self-serving (`eliotking01/economics-academy/seo/08-structured-data.md`, `Aetheria-Labs1/storefront-skills`, 2026) [OFICIAL]
9. HTML real de 25+ sitios hispanos de cerrajería/mudanzas/electricidad (títulos, descriptions, H1) [datos observados]
10. Log de verificación con cita textual de Mueller sobre H1 múltiples (`digibranders/cleanstart-web`, 2026-07-29) [OFICIAL vía terceros]

Búsquedas web ejecutadas (16): H1 múltiples Mueller 2025 · title rewrite 2025 study · leak titlematchScore NavBoost · meta description rewrite rate 2025 · FAQ/HowTo rich results status · Unbounce benchmark 2025 home services · FAQ retirement announcement May 2026 · keyword stuffing spam policies city names · internal links exact match Mueller/Illyes 2025 · emojis title/description 2025 · title length pixels 2026 mobile/desktop · click-to-call above the fold trust signals · June 2025 seven structured data types · review snippet LocalBusiness self-serving 2025 · H1 vs title split test SearchPilot · meta description CTA phone CTR local 2025 · 6 búsquedas adicionales de SERP en español quedaron sin ejecutar por agotamiento de cuota.
