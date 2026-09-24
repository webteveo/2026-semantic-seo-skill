# BLOQUE H — Técnico mínimo que importa en 2026 + schema + imágenes IA + enlazado interno a escala

**Para:** Benja (Montevideo) — sitios de servicios locales UY/AR, plantilla PHP+CSS+JS propia, cientos de páginas servicio × zona, schema LocalBusiness, CTA WhatsApp, imágenes IA.
**Fecha de investigación:** 24 de septiembre de 2026.
**Etiquetas:** [OFICIAL] doc/anuncio de Google, schema.org, OpenAI, Anthropic, Perplexity, Cloudflare · [FILTRACIÓN/PATENTE] · [TEST] estudio con datos · [OPINIÓN] criterio de terceros o mío · [posiblemente desactualizado] solo respaldo anterior a 2025.

## Nota de método (leer primero)

- La cuota de WebSearch de esta sesión estaba agotada (200/200) y el proxy de egreso bloquea `developers.google.com`, `schema.org`, `web.dev`, `support.google.com`, `searchengineland.com`, `seroundtable.com`, `ahrefs.com`, `zyppy.com`, `indexnow.org`, `platform.openai.com`, `docs.perplexity.ai`, etc.
- Solución: (1) descargué y parseé el **vocabulario oficial de schema.org** desde el repo oficial `schemaorg/schemaorg` (release 29.2 para el grafo; `versions.json` confirma que la **release vigente es 30.1, del 16-09-2026**); (2) leí los **docs de Google Search Central a través de un espejo textual en GitHub** (`bsisduck/google-search-ads-analytics-docs`, scrape del **08-06-2026**, misma estructura de rutas que developers.google.com) y de `lesishu/seo-guide-skill`; (3) leí directamente `support.claude.com` (Anthropic), el repo oficial de Cloudflare docs, `GoogleChrome/web-vitals`, `ai-robots-txt/ai.robots.txt`, `c2pa-org/specifications`; (4) para tests y citas de Googlers usé notas de investigación fechadas 2026 que citan fuente primaria (grabient, requestindexing.com, claude-seo, rybbit).
- Cuando la cita viene de un espejo, la URL que pongo es la **original de Google** (la que hay que citar) y anoto "espejo 2026-06-08". Verificá antes de publicar cualquier número que tenga [OPINIÓN] o "secundario".
- Conteo: 0 WebSearch exitosas (cuota), 20+ fuentes primarias abiertas vía WebFetch/curl (schema.org repo, 22 docs de Google en espejo, Anthropic, Cloudflare, web-vitals, C2PA, ai.robots.txt) + 8 secundarias fechadas 2026.

---

## 1. Core Web Vitals 2026: umbrales, peso real, mobile-first

### Umbrales vigentes

- [OFICIAL] Google, "Understanding Core Web Vitals and Google search results" — https://developers.google.com/search/docs/appearance/core-web-vitals (espejo 2026-06-08): "LCP occur within the first 2.5 seconds of the page starting to load", "INP of less than 200 milliseconds", "CLS score of less than 0.1".
- [OFICIAL] Librería `web-vitals` (Google Chrome), README — https://github.com/GoogleChrome/web-vitals (leído 2026-09-24, v5): umbrales `LCP [2500, 4000]`, `INP [200, 500]`, `CLS [0.1, 0.25]` (bueno / a mejorar / pobre).
- [OFICIAL] INP reemplazó a FID el 12-03-2024; FID retirado de las herramientas de Chrome el 09-09-2024 (cita secundaria de docs de Chrome en `indranilbanerjee/digital-marketing-pro`, 2026). No referenciar FID.
- La medición que cuenta es **de campo (CrUX), percentil 75, ventana móvil de 28 días**, no Lighthouse [OFICIAL, doc CWV].

### Cuánto pesa en ranking

- [OFICIAL] Google, "Understanding page experience in Google Search results" — https://developers.google.com/search/docs/appearance/page-experience (espejo 2026-06-08): "Google's core ranking systems look to reward content that provides a good page experience." Y en las FAQ: "There is no single signal. Our core ranking systems look at a variety of signals that align with overall page experience." Y: "Google Search always seeks to show the most relevant content, even if the page experience is sub-par. But for many queries, there is lots of helpful content available." Y: "getting good results in reports... doesn't guarantee that your pages will rank at the top."
- [OFICIAL] Doc CWV (mismo espejo): CWV "aligns with what our core ranking systems seek to reward" — es un conjunto de señales, no un "sistema" de ranking separado.
- [OPINIÓN] Checklist `sderosiaux/good-website-checklist` (2026): "Core Web Vitals are a real but weak ranking input, a tiebreaker rather than a lever." Coincide con lo que dice Google.
- [TEST] No encontré ningún test 2025-2026 que muestre movimiento de posiciones por pasar de "needs improvement" a "good". Los estudios de correlación anteriores a 2024 son [posiblemente desactualizado].

### Mobile-first indexing: estado final

- [OFICIAL] Google Search Central Blog, "Mobile indexing vLast final final" (junio 2024) — https://developers.google.com/search/blog/2024/06/mobile-indexing-vlast-final-final: **después del 5 de julio de 2024 Google rastrea e indexa para Search con Googlebot Smartphone**; un sitio cuyo contenido no es accesible en móvil no es indexable (cita vía `MariusYvard/NullToHero`, 2026). Googlebot Desktop puede seguir apareciendo en logs para otras features (Merchant, Jobs). Sin novedades 2025-2026: el tema está cerrado.

### Qué es "suficiente" para un sitio PHP estático de servicios

- Un sitio PHP que sirve HTML plano, sin frameworks JS pesados, con imágenes optimizadas, pasa CWV casi solo. Lo que rompe INP en estos sitios es JS de terceros (chats, mapas embebidos, GTM con muchos tags); lo que rompe LCP es la imagen hero sin `fetchpriority="high"` o con `loading="lazy"`; lo que rompe CLS son imágenes sin `width/height` y fuentes web sin `font-display: swap`.
- Checklist mínimo [OPINIÓN, alineado con docs de Google]: HTML cacheado (ver punto 8), hero `<img>` server-rendered con `fetchpriority="high"` y **sin** lazy, todo lo demás `loading="lazy" decoding="async"`, dimensiones explícitas siempre, CSS crítico inline pequeño, JS diferido (`defer`), un solo script de analítica, mapa de Google embebido solo con click (facade), fuentes del sistema o una sola familia con `swap`.
- No perseguir 100 en Lighthouse: con CrUX "good" en las tres métricas ya no hay nada más que ganar por este lado [OFICIAL, page-experience FAQ].

---

## 2. Indexación a escala: sitemaps, lastmod, Search Console, Indexing API, IndexNow, crawl budget

### Sitemaps: límites y lastmod

- [OFICIAL] Google, "Build and submit a sitemap" — https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap (última actualización reportada 2026-07-08; espejo 2026-06-08): "All formats limit a single sitemap to 50MB (uncompressed) or 50,000 URLs." Si superás el límite, sitemap index y enviás solo el index.
- [OFICIAL] Mismo doc: Google usa `<lastmod>` "if it's consistently and verifiably (for example by comparing to the last modification of the page) accurate"; el valor "should reflect the date and time of the last significant update to the page" (contenido principal, datos estructurados, enlaces; no un cambio de año de copyright).
- [OFICIAL] Mismo doc: "Google ignores `<priority>` and `<changefreq>` values."
- [OFICIAL] Google, "Large sitemaps": hasta **500 archivos de sitemap index por propiedad**; los sitemaps referenciados deben estar en el mismo directorio o más profundo (cita vía grabient 2026-08).
- [OPINIÓN] Gary Illyes (LinkedIn, 11-06-2024, citado en grabient 2026): la confianza en lastmod "es binaria: o confiamos o no". Un lastmod igual al timestamp del build en todas las URLs quema la señal para todo el sitio.
- **Para Benja:** cientos o pocos miles de URLs entran en un solo sitemap, pero conviene **segmentar por tipo** (`sitemap-servicios.xml`, `sitemap-zonas.xml`, `sitemap-blog.xml`, `sitemap-index.xml`) porque el informe de Search Console se filtra por sitemap y ves qué segmento no se indexa. `lastmod` **solo cuando cambió el contenido real** (guardá una fecha de modificación por página en tu generador PHP; no uses `date('c')` en cada request).

### URL Inspection / Solicitar indexación: cuota

- [OFICIAL] Google, "Ask Google to recrawl your URLs" — https://developers.google.com/search/docs/crawling-indexing/ask-google-to-recrawl (espejo 2026-06-08): "there's a quota for submitting individual URLs and requesting a recrawl multiple times for the same URL won't get it crawled any faster." Hay que ser propietario o usuario completo de la propiedad.
- [OPINIÓN] La cuota concreta no está publicada; la práctica reporta ~10-12 solicitudes por propiedad y día. No sirve como mecanismo a escala: para 300 páginas nuevas, el mecanismo es el sitemap + enlazado interno.
- [OFICIAL] Search Console "Recommendations" (lanzadas en el blog de Search Central en agosto 2024 y ampliadas en 2025) — sugieren sitemaps faltantes, páginas en tendencia, etc. [posiblemente desactualizado: no pude abrir el post 2025]. Novedad 2026 relevante: **informe "Search generative AI performance" en Search Console** (blog 2026-06-03, https://developers.google.com/search/blog/2026/06/gen-ai-performance-reports, cita secundaria) y toggle "Search generative AI" en configuración de GSC (Google dice que no es señal de ranking; secundario, `gameworkerkim/vibe-investing`).

### Indexing API: texto oficial y qué pasa si se abusa

- [OFICIAL] Google, Indexing API Quickstart — https://developers.google.com/search/apis/indexing-api/v3/quickstart (última actualización reportada 2026-07-16): "Currently, the Indexing API can only be used to crawl pages with either `JobPosting` or `BroadcastEvent` embedded in a `VideoObject`." Cuota por defecto **200 publish requests/día**, lotes de 100 URLs que igual cuentan por URL (citado en requestindexing.com y grabient, 2026).
- [OFICIAL] Google, "Using the Indexing API" — https://developers.google.com/search/apis/indexing-api/v3/using-api (2026-07-16): "Don't circumvent our submission limits." (cita vía grabient).
- [OPINIÓN, Googler] John Mueller, Bluesky, 23-05-2025: "We see a lot of spammers misuse the Indexing API... I'd recommend sticking to documented use-cases." (cita vía `harlan-zw/requestindexing.com`, research 2026).
- [OPINIÓN, Googler] Gary Illyes, SEO Office Hours abril 2024: el acceso para verticales no soportados puede revocarse "de la noche a la mañana" sin aviso (misma fuente).
- [OFICIAL] El doc de JobPosting recomienda la API **en lugar de** sitemaps para avisos de empleo (espejo 2026-06-08) — o sea, sigue siendo un canal de nicho.
- **¿Google endureció esto en 2025-2026?** No hay anuncio formal de cambio de política; lo que hay es (a) el texto restrictivo intacto y actualizado en julio 2026, (b) Googlers advirtiendo públicamente sobre spammers en 2025, (c) reportes de cuentas con acceso revocado. Riesgo real: perder la cuenta de Cloud/servicio y quedar marcado. **Recomendación: no usarla para páginas servicio×zona.** El "truco" de envolver LocalBusiness en un JobPosting falso viola además las políticas de datos estructurados (contenido engañoso → acción manual).

### IndexNow (Bing y compañía)

- [OFICIAL] IndexNow FAQ — https://www.indexnow.org/faq y `searchengines.json` (verificado 2026-08-16 por grabient): participan **Bing, Yandex, Naver, Seznam, Yep, Internet Archive, Amazon**; **Google no participa** (anunció un "test" en nov-2021 y nunca se sumó). Límite: 10.000 URLs por POST; clave de 8-128 caracteres en `/{key}.txt`.
- [OPINIÓN] El índice de Bing es el sustrato de DuckDuckGo, Ecosia, Yahoo y **Copilot**; varias fuentes 2026 afirman que **ChatGPT Search recupera resultados a través del índice de Bing** (grabient, good-website-checklist), pero **OpenAI no lo documenta oficialmente**: lo que sí documenta es su propio crawler OAI-SearchBot (ver punto 8). Tratarlo como "probable, no confirmado".
- **Para Benja:** IndexNow cuesta 20 líneas de PHP (un `file_get_contents` a `https://api.indexnow.org/indexnow` con la lista de URLs cuando publicás o editás). Gratis, sin riesgo, y cubre Bing/Copilot. Registrar también Bing Webmaster Tools (importa la verificación desde GSC).

### Crawl budget para sitios chicos

- [OFICIAL] Google, "Large site owner's guide to managing your crawl budget" — https://developers.google.com/search/docs/crawling-indexing/large-site-managing-crawl-budget (última actualización reportada 2026-07-22; espejo 2026-06-08): la guía es para "Large sites (1 million+ unique pages) with content that changes moderately often" y "Medium or larger sites (10,000+ unique pages) with very rapidly changing content", o sitios con mucho "Discovered - currently not indexed". Si no es tu caso: "you don't need to read this guide."
- [OFICIAL] Google, "Myths about crawling" (2025-12-18): las 4xx (salvo 429) no gastan crawl budget (cita vía grabient).
- **Para Benja:** con <10k URLs el crawl budget **no es un problema de cuota**, es un problema de **calidad**: si ves "Discovered - currently not indexed" masivo en páginas zona, Google está decidiendo que no valen la pena (ver punto 8, noindex, y bloque de contenido).

---

## 3. Schema recomendado para servicio local

### Qué reconoce Google (rich results) vs qué es solo semántico

- [OFICIAL] Google, "Local Business (LocalBusiness) structured data" — https://developers.google.com/search/docs/appearance/structured-data/local-business (espejo 2026-06-08). **Requeridas:** `name` y `address` (PostalAddress, "Include as many properties as possible"). **Recomendadas:** `aggregateRating` (solo si capturás reseñas de *otros* negocios), `department`, `geo` (lat/long con ≥5 decimales), `menu`, `openingHoursSpecification`, `priceRange` (máx. 100 caracteres, "$$" o rango), `review` (idem, terceros), `servesCuisine`, `telephone` (con código de país y área), `url` ("Fully-qualified URL of the specific business location"). Guía: usar el **subtipo más específico** de LocalBusiness; para varios tipos usar **array** en `@type`, no `additionalType`.
- [OFICIAL] Google, "Structured data general guidelines" — https://developers.google.com/search/docs/appearance/structured-data/sd-policies (espejo 2026-06-08): "Don't mark up content that is not visible to readers of the page"; "Try to use the most specific applicable type and property names defined by schema.org"; "All image URLs specified in structured data must be crawlable and indexable"; para varias entidades, anidar o **enlazar con `@id`**. Violación → acción manual → pierde rich results (no afecta ranking directamente). Google "does not guarantee that your structured data will show up".
- [OFICIAL] Google, "Search Gallery" (espejo 2026-06-08): features vivas que te importan: **Local business, Breadcrumb, Review snippet, Organization, Image metadata, Q&A, FAQ (ya sin resultados desde 2026-05-07, ver punto 4)**. **HowTo y Sitelinks search box ya no figuran.**
- [OFICIAL] Google, "AI features and your website" — https://developers.google.com/search/docs/appearance/ai-features (espejo 2026-06-08): "There are no additional requirements to appear in AI Overviews or AI Mode" y "There's also no special schema.org structured data that you need to add."
- [OFICIAL] Google, "AI optimization guide" — https://developers.google.com/search/docs/fundamentals/ai-optimization-guide (anunciada 2026-05-15, actualizada 2026-07-10; cita vía claude-seo): mythbusting — no hace falta `llms.txt`, ni "chunking", ni reescrituras para IA, ni **sobreinvertir en datos estructurados** para features de IA. "optimizing for generative AI search is optimizing for the search experience, and thus still SEO."
- [TEST] Ahrefs, "We tracked 1,885 pages adding schema" — https://ahrefs.com/blog/schema-ai-citations/ (2026-05-11, act. 2026-06-09): 1.885 páginas que agregaron JSON-LD entre ago-2025 y mar-2026 vs 4.000 de control, ventana 30 días: **AI Overviews −4,6 % (significativo), AI Mode +2,4 % y ChatGPT +2,2 % (indistinguibles de cero)**. Conclusión: agregar schema no sube citas en IA. Advertencias del propio estudio: 30 días, solo JSON-LD en HTML (no inyectado por JS).
- Conclusión práctica: `Service`, `areaServed`, `hasOfferCatalog`, `knowsAbout`, `potentialAction`, `sameAs`, `serviceType`, `provider` son **semánticos** (ningún rich result los usa). Sirven para desambiguar entidades y para validadores; no esperes CTR ni citas por ellos. Lo que sí renderiza Google en local: el **knowledge panel** (alimentado sobre todo por GBP), estrellas **solo con reseñas de terceros**, y **breadcrumbs**.

### Vocabulario oficial (schema.org 30.1, 16-09-2026) — verificado en el repo oficial

- Subtipos directos de `HomeAndConstructionBusiness`: **Electrician, GeneralContractor, HVACBusiness, HousePainter, Locksmith, MovingCompany, Plumber, RoofingContractor**. Definición: "A HomeAndConstructionBusiness is a LocalBusiness that provides services around homes and buildings. As a LocalBusiness it can be described as a provider of one or more Service(s)."
- Subtipos de `AutomotiveBusiness`: AutoBodyShop, AutoDealer, AutoPartsStore, AutoRental, **AutoRepair**, AutoWash, GasStation, MotorcycleDealer, MotorcycleRepair. **No existen** `TowingService`, `RoadsideAssistance` ni `AutoTowing`.
- **No existen** `CleaningService`, `Carpenter`, `PestControl`, `Waterproofing`, `ContactAction`. `EmergencyService` existe pero sus subtipos son FireStation/Hospital/PoliceStation ("An emergency service, such as a fire station or ER"): no usarlo para auxilio mecánico.
- `ProfessionalService`: el propio schema.org dice "The general ProfessionalService type for local businesses was deprecated due to confusion with Service" — **no lo uses**.
- Propiedades y rangos (oficial): `areaServed` → GeoShape | AdministrativeArea | Place | Text (dominio: Service, Organization, Offer, ContactPoint…); `serviceArea` está **supersededBy areaServed**; `serviceType` → Text (dominio Service); `provider` → Organization | Person; `hasOfferCatalog` → OfferCatalog (Organization, Person, Service); `makesOffer` → Offer (Organization, Person); `priceRange` → Text (LocalBusiness); `openingHoursSpecification` → OpeningHoursSpecification (Place); `geo` → GeoCoordinates | GeoShape; `GeoCircle` (subtipo de GeoShape) con `geoMidpoint` y `geoRadius` (metros); `City` es subtipo de `AdministrativeArea`; `knowsAbout` → Thing | Text | URL ("suggesting possible expertise but not implying it"); `sameAs` → URL; `potentialAction` → Action; `branchOf` supersededBy `parentOrganization`; `ContactPoint` tiene `telephone, contactType, areaServed, availableLanguage, contactOption, hoursAvailable`.
- WhatsApp: como **no existe `ContactAction`**, el CTA se modela como `contactPoint` → `ContactPoint` con `url: "https://wa.me/598…"` (o `telephone`) y, si querés, `potentialAction` → `CommunicateAction` con `target` → `EntryPoint.urlTemplate`. Google no renderiza nada de esto: es puro semántico.

### Tabla nicho → @type exacto

| Nicho de Benja | `@type` recomendado (existe en 30.1) | Alternativa / notas |
|---|---|---|
| Cerrajería | `Locksmith` | — |
| Mudanzas / fletes | `MovingCompany` | — |
| Electricista | `Electrician` | — |
| Yeso / construcción en seco (durlock) | `GeneralContractor` | No hay DrywallContractor; `serviceType: "construcción en seco"`, `knowsAbout` |
| Aire acondicionado (instalación/service) | `HVACBusiness` | — |
| Impermeabilización (techos/azoteas) | `RoofingContractor` | Si es membranas en paredes/tanques: `GeneralContractor`; `serviceType: "impermeabilización"` |
| Pérgolas / decks | `GeneralContractor` | No existe Carpenter; `serviceType: "pérgolas"` |
| Casas modulares / prefabricadas | `GeneralContractor` | Si vende unidades: agregar `Product` u `Offer` en `makesOffer` |
| Auxilio mecánico / grúa 24 h | `AutoRepair` | No existe TowingService; `serviceType: "auxilio mecánico y remolque"`; `openingHoursSpecification` 00:00-23:59 |
| Limpieza (hogar/oficinas/fin de obra) | `LocalBusiness` (o `HomeAndConstructionBusiness`) | No existe CleaningService; `DryCleaningOrLaundry` es solo tintorería; usar `serviceType` |
| Baños químicos (alquiler) | `LocalBusiness` | `makesOffer` → `Offer` → `itemOffered: Service "alquiler de baños químicos"` |
| Steel framing | `GeneralContractor` | `serviceType: "steel framing"` |
| Galpones / tinglados | `GeneralContractor` | idem |
| Plomería / sanitaria | `Plumber` | — |
| Pintura | `HousePainter` | — |

Cuando dudes entre dos, podés poner array: `"@type": ["GeneralContractor", "LocalBusiness"]` (Google lo acepta: "use an array" en el doc LocalBusiness).

### Otras decisiones de modelado

- `@id` estable por entidad: `{url}/#negocio` para el LocalBusiness principal; `{url}/#website`; cada página servicio×zona referencia `"provider": {"@id": "{url}/#negocio"}`. Es exactamente el patrón que Google pide para vincular entidades (sd-policies).
- `address` es **requerida** por Google incluso para negocios de área de servicio; si el negocio no atiende público, usá la dirección real (la misma del GBP) y no inventes una. Si de verdad no hay dirección, poné al menos `addressLocality`, `addressRegion`, `addressCountry` (Google dice "as many properties as possible", no "todas").
- `areaServed`: en la home, lista de `City`/`AdministrativeArea` (departamentos/partidos) + opcional `GeoCircle`; en cada página zona, **una sola** `City`/`Place` con `containedInPlace` al departamento. `Text` también es válido pero menos útil.
- `openingHoursSpecification` solo si es real (24 h en auxilio y cerrajería de urgencia es habitual y legítimo).
- `priceRange`: "$$" o "Presupuesto sin cargo"; máx. 100 caracteres.
- `image`: URL absoluta, rastreable, idealmente **foto real** (ver punto 6); si es IA, igual sirve pero no la marques como "nuestro equipo".
- `sameAs`: GBP no tiene URL canónica "pública" estable; usá Instagram/Facebook/LinkedIn/ficha de directorio. No inventar Wikidata.
- `aggregateRating` / `review`: **no** en tu propio LocalBusiness (ver punto 5).

---

## 4. FAQPage: estado 2026

- [OFICIAL] Google, "FAQ (FAQPage, Question, Answer) structured data" — https://developers.google.com/search/docs/appearance/structured-data/faqpage (espejo 2026-06-08), aviso al inicio del doc: "**Upcoming deprecation:** As of May 7, 2026, FAQ rich results are no longer appearing in Google Search. We will be dropping the FAQ search appearance, rich result report, and support in the Rich results test in June 2026. To allow time for adjusting your API calls, support for the FAQ rich result in the Search Console API will be removed in August 2026." El doc todavía conserva el texto de agosto 2023: "FAQ rich results are only available for well-known, authoritative websites that are government-focused or health-focused."
- [OFICIAL] Registro de cambios de Search Central — https://developers.google.com/search/updates#removing-faq-rich-result (2026-05-07). Cronología secundaria (grabient/claude-seo): 2026-05-07 dejan de aparecer; junio 2026 se elimina el filtro de apariencia y el informe; agosto 2026 se elimina de la API.
- [OFICIAL] HowTo: rich results eliminados en septiembre 2023 (https://developers.google.com/search/blog/2023/08/howto-faq-changes) y ya no figura en la galería 2026.
- ¿Sigue valiendo la pena marcar FAQ? Evidencia:
  - [OFICIAL] Google (ai-features + AI optimization guide 2026): no hay schema especial para IA; no sobreinvertir.
  - [TEST] Ahrefs 2026-05: agregar schema no subió citas en AIO/AI Mode/ChatGPT.
  - [OPINIÓN] claude-seo (2026-06): "the markup still aids AI Mode" — sin datos.
  - **Recomendación:** mantener las FAQ **como contenido visible en HTML** (eso sí lo leen Google y los LLM), y el JSON-LD `FAQPage` como opcional de bajo costo: no molesta, no da acción manual si el contenido es visible, y sirve para Bing/otros. No dedicarle esfuerzo ni esperar nada. Si tu generador ya lo emite, dejalo; si no, no lo priorices.

---

## 5. BreadcrumbList, reseñas y "self-serving reviews"

### BreadcrumbList

- [OFICIAL] Google, "Breadcrumb (BreadcrumbList) structured data" — https://developers.google.com/search/docs/appearance/structured-data/breadcrumb (espejo 2026-06-08). Requeridas: `itemListElement` (array de `ListItem`) con `position`, `name`, `item` (URL). "If the breadcrumb is the last item in the breadcrumb trail, `item` is not required. If `item` isn't included for the last item, Google uses the URL of the containing page." Se pueden declarar varias rutas (varios `BreadcrumbList` en un array).
- [OFICIAL] Disponibilidad: "available on desktop in all regions and languages" — en móvil, desde 2024 Google muestra solo el dominio/nombre del sitio en la mayoría de los resultados, así que el beneficio visual del breadcrumb es sobre todo desktop. Sigue valiendo para entender jerarquía.
- Implementación para `/servicio/zona`: Inicio › {servicio} › {zona}. El breadcrumb visible en HTML debe coincidir con el JSON-LD (sd-policies: no marcar lo que no se ve).

### Review / AggregateRating en LocalBusiness

- [OFICIAL] Google, "Review snippet (Review, AggregateRating) structured data" — https://developers.google.com/search/docs/appearance/structured-data/review-snippet (espejo 2026-06-08), texto de la guía: "**If the entity that's being reviewed controls the reviews about itself, their pages that use LocalBusiness or any other type of Organization structured data are ineligible for star review feature.**" Además: "Ratings must be sourced directly from users" y no "rely on human editors to create, curate, or compile ratings information for local businesses." `AggregateRating` requiere `itemReviewed` (o el padre si está anidado), `ratingCount` o `reviewCount`, y `ratingValue`.
- Esta regla nació en septiembre 2019 y **sigue vigente en el doc de junio 2026**: no hay estrellas para tu propio negocio ni para tu propia Organization. Los sitios que las muestran vía plugins están violando la guía y son candidatos a acción manual (secundario: "Stricter enforcement 2024", `sickn33/agentic-awesome-skills`) [OPINIÓN].
- ¿Marcar reseñas de Google (GBP) en tu sitio? **No**: (1) las controla la entidad reseñada → self-serving; (2) no son "sourced directly from users" en tu sitio, son copiadas; (3) los ToS de Google Maps Platform restringen el cacheo/redistribución del contenido de Places. Podés **mostrarlas** como texto/widget legítimo (con enlace a la ficha) pero **sin** `Review`/`AggregateRating` en tu LocalBusiness. La única forma legítima de estrellas es que un **tercero** (directorio, marketplace) marque reseñas sobre vos en *su* sitio.

---

## 6. Imágenes generadas con IA en sitios de servicios

### Postura oficial de Google

- [OFICIAL] Google, "Google Search's guidance about AI-generated content" — https://developers.google.com/search/docs/fundamentals/using-gen-ai-content (espejo 2026-06-08): usar IA "to generate many pages without adding value for users may violate Google's spam policy on scaled content abuse"; "If you're automatically generating content, consider adding information on how your content was created" (divulgación opcional). Sobre imágenes, el doc remite a comercio: "AI-generated images must contain metadata using the IPTC DigitalSourceType TrainedAlgorithmicMedia metadata" (requisito de **Merchant Center**, política https://support.google.com/merchants/answer/14743464), y destaca el alt text como metadato crítico.
- [OFICIAL] Google, "Image metadata in Google Images" — https://developers.google.com/search/docs/appearance/structured-data/image-license-metadata (espejo 2026-06-08): Google lee IPTC `DigitalSourceType` con valores como "trainedAlgorithmicMedia: The image was created algorithmically using a model derived from sampled content" (también `compositeSynthetic`, `algorithmicMedia`, `compositeWithTrainedAlgorithmicMedia`), y muestra credenciales C2PA en "About this image" (si la imagen "was edited with AI tools"). **No hay una etiqueta "AI-generated" que se imprima en la grilla de Google Images**; la información aparece en "About this image".
- [OFICIAL] Google, Spam policies — https://developers.google.com/search/docs/essentials/spam-policies (act. 2026-05-15): **no existe política de "spam de imágenes" ni mención a imágenes IA**. Sí existe "Scaled content abuse" ("many pages are generated for the primary purpose of manipulating search rankings and not helping users") y "Doorway abuse" (ver punto 8).
- [OPINIÓN, Googler] Gary Illyes, informal (~2025-08-11, vía grabient): "AI generated image doesn't impact the SEO. Not direct."
- [OFICIAL] SynthID (marca de agua de Google en imágenes de Imagen/Gemini) — verificación ampliada a Lens / AI Mode / Circle to Search el **2026-05-19**; C2PA en "About this image" desde 2024-09-17 (cita secundaria grabient; blog.google bloqueado en esta sesión). Spec C2PA vigente: **2.4** (repo oficial, leído 2026-09-24).
- [OPINIÓN/QRG] Search Quality Rater Guidelines: actualización 2025-01-23 (definió IA generativa, scaled content abuse, filler) y **2025-09-11** (182 páginas; nuevas categorías YMYL "Government, Civics & Society"; contenido YMYL puramente IA sin revisión ni valor propio → "Lowest") — citas secundarias (`Yahya-Halim/Websites`, `claude-seo`). No pude abrir el PDF. Sobre **imágenes** IA la QRG no las prohíbe: lo que penaliza es que la página engañe o no aporte esfuerzo/originalidad.

### Riesgos concretos para un sitio de servicios

1. **Engaño = E-E-A-T roto**: una imagen IA presentada como "trabajo realizado en Pocitos" o "nuestro equipo" es contenido engañoso; si un rater o un cliente lo detecta, se cae la confianza (T es "lo más importante" en E-E-A-T según QRG). Y si lo usás en anuncios, viola políticas de Ads.
2. **Duplicación a escala**: la misma imagen IA en 300 páginas zona no suma nada y refuerza la lectura de "doorway/plantilla".
3. **Conversión**: no hay test 2025-2026 sólido específico de servicios locales; la evidencia indirecta (QRG "Original images/video — not stock photos") y la lógica de un rubro donde el cliente quiere ver el camión, el taller, la obra, van en contra de las imágenes IA como prueba social [OPINIÓN].
4. **Legal (UY/AR)**: caras sintéticas "de empleados" o "clientes" pueden chocar con publicidad engañosa (Ley 17.250 UY / Ley 24.240 AR) [OPINIÓN, no verificado con abogado].

### Buenas prácticas (lo que sí hacer)

- Fotos reales para: héroe de la home, "equipo", "trabajos realizados", vehículos, local. Pedile al cliente 10-15 fotos de celular; valen más que cualquier render.
- IA solo para **ilustraciones genéricas** (iconos, diagramas "cómo funciona un split", fondos), y nunca como evidencia de obra.
- **Alt honesto y descriptivo** ("Ilustración de instalación de aire acondicionado split" vs "Instalación realizada en Carrasco"). Nombre de archivo descriptivo (`instalacion-split-ilustracion.webp`) [OFICIAL, google-images].
- Incrustar IPTC `DigitalSourceType = trainedAlgorithmicMedia` con exiftool en las imágenes IA (`-XMP-iptcExt:DigitalSourceType="https://cv.iptc.org/newscodes/digitalsourcetype/trainedAlgorithmicMedia"`); no cuesta nada, es lo que Google pide en comercio y te protege si mañana lo exigen en orgánico.
- Mezclar: en páginas zona, 1 foto real del rubro (aunque sea del mismo negocio) + 0-1 ilustración; nunca "obra en {zona}" con imagen sintética.
- Si usás Imagen/Gemini, las imágenes ya traen SynthID; no intentes quitarlo.

---

## 7. Enlazado interno a escala

### Qué dice Google

- [OFICIAL] Google, "Link best practices" — https://developers.google.com/search/docs/crawling-indexing/links-crawlable (espejo 2026-06-08): "Good anchor text is descriptive, reasonably concise, and relevant to the page that it's on and to the page it links to." "Every page you care about should have a link from at least one other page on your site." Sobre cantidad: no hay número; "if you think it's too much, then it probably is."
- [posiblemente desactualizado] La vieja guía "fewer than 100 links" fue retirada (Matt Cutts 2009 explicó que venía del límite de 100 KB del indexador); hoy no existe umbral documentado (artículo `linkagent`, 2026-08-09, resumiendo la historia).
- [FILTRACIÓN/PATENTE] "Reasonable surfer" (patente de Google, 2010, renovada): el valor de un enlace escala con la probabilidad de que un usuario lo clickee; los enlaces de boilerplate (header/footer/sidebar) valen menos que los del cuerpo. Se cita como justificación de que los mega-footers de 200 links diluyen (linkagent 2026) [posiblemente desactualizado en detalle, vigente en principio].

### Evidencia 2025-2026 y estudios

- [TEST] Zyppy, estudio de 23 millones de enlaces internos en 1.800 sitios — https://zyppy.com/seo/internal-links/seo-study/ (2022, vigente como único dataset grande; citado en 2026 por `youtube-jono/seo-agent`): las URLs con **40-44 enlaces internos entrantes** promedian ~4× los clics de las que tienen 0-4; la relación **se invierte pasados ~45-50**; las páginas con al menos **un anchor exact-match interno** obtuvieron ~5× más tráfico; la **variedad de anchors** fue el correlato más fuerte, sin techo visible. [posiblemente desactualizado: dataset 2022].
- [TEST] Kevin Indig / Gauge (feb-2026): en 1,2 M respuestas de ChatGPT y 30 M citas, **44,2 % de las citas salen del primer 30 % de la página** (cita secundaria, `MrSmithNL`). Aplica a dónde poner los enlaces y la respuesta: arriba.
- [OPINIÓN] Regla de un tercio: ningún anchor debería superar ~1/3 del perfil de anchors entrantes de una página (linkagent 2026).
- No encontré un estudio Ahrefs 2025-2026 específico de profundidad de clic; "≤3 clics desde la home" es heurística de la industria, coherente con crawl y con el reasonable surfer [OPINIÓN].

### Arquitectura recomendada para servicio × zona (Benja)

1. **Hub país → departamento/provincia → zona**: `/cerrajeria/` (hub servicio) → `/cerrajeria/montevideo/` (hub departamento: lista de barrios con 1 línea de contexto cada uno) → `/cerrajeria/montevideo/pocitos/`. Cada página zona a ≤3 clics de la home.
2. **Vecinos reales**: en cada página zona, 4-8 enlaces a barrios **geográficamente contiguos** (Pocitos ↔ Punta Carretas, Buceo, Parque Batlle), no aleatorios ni "todos los barrios". Mantené una tabla de adyacencias en tu generador. Anchors variados: "cerrajero en Buceo", "urgencias en Punta Carretas", "también atendemos Parque Batlle".
3. **Servicio ↔ servicio en la misma zona**: 2-4 enlaces cruzados relevantes (cerrajería ↔ electricista de urgencia, no cerrajería ↔ baños químicos).
4. **Breadcrumb** visible + JSON-LD (punto 5).
5. **Cuerpo > boilerplate**: los enlaces que importan van en el texto (párrafo de "zonas cercanas" y "otros servicios"), no solo en footer/menú.
6. **Menú**: header con ≤10 enlaces (servicios principales); **nada de mega-footer con 200 zonas**. Razones: (a) valor diluido por reasonable surfer; (b) patrón visual de doorway; (c) INP/CLS por DOM enorme; (d) UX móvil. Si querés un índice completo, hacé una **página "Zonas que cubrimos"** (HTML sitemap) enlazada desde el footer, con los barrios agrupados por departamento.
7. **Cero huérfanas**: al generar una página nueva, el generador debe insertarla en su hub, en los vecinos y en el HTML sitemap el mismo día (Google: "Every page you care about should have a link from at least one other page").
8. **Presupuesto de enlaces por página zona**: ~10-20 internos en cuerpo + nav. Objetivo de enlaces entrantes por página zona importante: 10-40 (Zyppy); las de barrios chicos no necesitan más de 5-8.
9. **Auditoría**: crawl mensual (Screaming Frog o script propio) verificando: profundidad ≤3, entrantes ≥3, sin huérfanas, anchors únicos por destino ≥3 variantes.

---

## 8. Otros técnicos

### hreflang, canonical, paginación, noindex

- [OFICIAL] Google, "Localized versions" — https://developers.google.com/search/docs/specialty/international/localized-versions (espejo 2026-06-08): hreflang solo cuando tenés versiones por idioma/región; un sitio en un solo idioma sin variantes no lo necesita. Códigos válidos: ISO 639-1 + ISO 3166-1 alfa-2 (`es-UY`, `es-AR`); `es-419` **no** es válido; no se puede poner solo el país. **Para Benja:** un sitio `.uy` y otro `.com.ar` separados = **no hreflang**. Solo si un mismo dominio tiene `/uy/` y `/ar/` con el mismo contenido adaptado, ahí sí `es-UY`/`es-AR` + `x-default`.
- [OFICIAL] Google, "How to specify a canonical" — https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls (act. 2026-07-10; espejo 2026-06-08): redirects y `rel="canonical"` son "strong signal", sitemap "weak signal"; "these methods can stack". Canonical **autorreferente absoluto** en toda página (no lo exige, pero evita que parámetros UTM/`?ref=` creen duplicados) [OPINIÓN estándar].
- Paginación: no aplica a servicio×zona; si el blog pagina, `rel=prev/next` ya no lo usa Google desde 2019 [posiblemente desactualizado pero vigente]; canonical propio en cada página de la serie.
- **noindex de zonas sin tráfico**: no hay doc de Google que lo pida. Criterio: si una página zona no tiene contenido único (datos del barrio, casos, tiempos de llegada, precios de referencia, FAQ locales) y lleva 6 meses en "Crawled/Discovered - not indexed", **mejorala o fusionala** en el hub del departamento con 301; noindex es la tercera opción. Cientos de páginas plantilla idénticas cambiando el nombre del barrio encajan en la definición oficial de doorway: "multiple domain names or pages targeted at specific regions or cities that funnel users to one page" [OFICIAL, spam-policies, act. 2026-05-15]. La diferencia entre "página local útil" y "doorway" es contenido y utilidad, no el schema.

### Imágenes: lazy load, formatos

- [OFICIAL] Google, "Google Images SEO best practices" — https://developers.google.com/search/docs/appearance/google-images (espejo 2026-06-08): formatos soportados "BMP, GIF, JPEG, PNG, WebP, SVG, and AVIF"; `<picture>`/`srcset` con `src` de respaldo ("some browsers and crawlers don't understand these attributes"); nombres de archivo descriptivos; alt informativo sin keyword stuffing; sitemap de imágenes opcional; CDN permitido.
- [OFICIAL] Google, "Fix lazy-loaded content" — https://developers.google.com/search/docs/crawling-indexing/javascript/lazy-loading (espejo 2026-06-08): usar lazy-load nativo del navegador o IntersectionObserver; "Google Search does not interact with your page" (nada que dependa de scroll); verificar con URL Inspection que el contenido esté en el HTML renderizado.
- Práctica: AVIF con fallback WebP/JPEG vía `<picture>`; héroe sin lazy y con `fetchpriority="high"`; el resto `loading="lazy" decoding="async"`; `width`/`height` siempre.

### PHP caching, Cloudflare, HTTPS

- [OPINIÓN, ingeniería] Para PHP estático: generar HTML a disco (build) o cache de página completa (APCu/archivo) con `Cache-Control: max-age=0, s-maxage=600, stale-while-revalidate=86400` en HTML y `public, max-age=31536000, immutable` en assets con hash; Brotli; HTTP/2 o 3 en el edge. Cloudflare (plan gratis) delante: cache de HTML con "Cache Everything" + purge en publish, HTTPS automático, HTTP/3.
- **Cuidado con Cloudflare y bots IA** [OFICIAL, Cloudflare docs, repo oficial leído 2026-09-24]: desde el **15 de septiembre de 2026** los nuevos defaults bloquean bots clasificados "Training" o "Agent" en páginas con anuncios y dejan pasar "Search"; los crawlers mixtos (search+training) se bloquean en configuraciones anti-training. Además existe el **managed robots.txt** que Cloudflare **antepone** al tuyo con `Disallow: /` para GPTBot, ClaudeBot, CCBot, Google-Extended, Applebot-Extended, meta-externalagent, Amazonbot, Bytespider (medido en un sitio real el 2026-08-16, grabient). Si querés visibilidad en asistentes, **revisá Security → Bot traffic** y desactivá el bloqueo de robots.txt gestionado o ajustá por categoría.
- HTTPS: obligatorio (page-experience self-assessment "Uses HTTPS security") [OFICIAL].

### robots.txt y crawlers IA (GEO)

Docs oficiales y comportamiento (verificado 2026-09):

- [OFICIAL] Google, crawlers comunes — https://developers.google.com/search/docs/crawling-indexing/google-common-crawlers#google-extended (act. 2026-07-14): `Google-Extended` controla entrenamiento de Gemini y grounding en Gemini Apps/Vertex AI; "does not impact a site's inclusion in Google Search nor is it used as a ranking signal in Google Search". [OFICIAL] ai-features: AI Overviews/AI Mode se controlan con `nosnippet`, `data-nosnippet`, `max-snippet`, `noindex` de Googlebot, **no** con Google-Extended.
- [OFICIAL] OpenAI, bots — https://developers.openai.com/api/docs/bots (leído por rybbit 2026-09-13): `GPTBot` = entrenamiento; `OAI-SearchBot` = resultados de ChatGPT search ("a webmaster can allow OAI-SearchBot in order to appear in search results while disallowing GPTBot"; sitios que bloquean OAI-SearchBot "will not be shown in ChatGPT search answers"); `ChatGPT-User` = fetch a pedido del usuario, robots.txt puede no aplicar.
- [OFICIAL] Anthropic — https://support.claude.com/en/articles/8896518 (leído directo 2026-09-24): `ClaudeBot` (entrenamiento; bloquearlo excluye contenido futuro de datasets), `Claude-User` (fetch a pedido; bloquearlo "may reduce your site's visibility for user-directed web search"), `Claude-SearchBot` (calidad de búsqueda; bloquearlo "may reduce your site's visibility and accuracy in user search results"). Todos respetan robots.txt y `Crawl-delay`.
- [OFICIAL] Perplexity — https://docs.perplexity.ai/guides/bots (vía rybbit 2026-09-13): `PerplexityBot` indexa y respeta robots.txt; `Perplexity-User` "generally ignores robots.txt rules" (publican IPs para firewall).
- [OFICIAL/COMUNIDAD] `ai-robots-txt/ai.robots.txt` (tabla actualizada 2026): `Applebot-Extended` = entrenamiento de modelos Apple (Applebot normal = Siri/Spotlight search); `Bingbot` = Bing/Copilot; `Amazonbot` = Alexa; `Meta-ExternalAgent` = entrenamiento; `CCBot` = Common Crawl.
- [TEST] Log study ~900 dominios (sep-2025 → abr-2026, vía `MrSmithNL`): en sitios chicos, los crawlers frontera casi no pasan (0 requests en muchos); Ahrefs (2026-06-15): 97 % de los `llms.txt` de 137.000 dominios no recibieron ni un request. **No pierdas tiempo con llms.txt** (Google también lo dice).

Decisión para un sitio de servicios que **quiere leads** de cualquier fuente: **permitir todos los bots de búsqueda/asistente**, y decidir libremente sobre los de entrenamiento (bloquearlos no te saca de ChatGPT search ni de AI Overviews; permitirlos no te mete). Mi recomendación: permitir todo salvo scrapers puros (CCBot, Bytespider), porque el "costo" de que un modelo aprenda que "X es cerrajero en Pocitos" es cero y el beneficio potencial es una mención.

#### robots.txt recomendado

```
# robots.txt — sitio de servicios locales (UY/AR)
User-agent: *
Allow: /
Disallow: /admin/
Disallow: /includes/
Disallow: /tmp/
Disallow: /*?utm_
Disallow: /*?ref=
Disallow: /buscar

# Buscadores clásicos
User-agent: Googlebot
Allow: /
User-agent: Bingbot
Allow: /

# Asistentes / búsqueda IA (dejarlos entrar: son fuente de leads)
User-agent: OAI-SearchBot
Allow: /
User-agent: ChatGPT-User
Allow: /
User-agent: Claude-SearchBot
Allow: /
User-agent: Claude-User
Allow: /
User-agent: PerplexityBot
Allow: /
User-agent: Applebot
Allow: /
User-agent: Amazonbot
Allow: /

# Entrenamiento (decisión de negocio; permitirlos no da ni quita visibilidad en búsqueda)
User-agent: GPTBot
Allow: /
User-agent: ClaudeBot
Allow: /
User-agent: Google-Extended
Allow: /
User-agent: Applebot-Extended
Allow: /
User-agent: Meta-ExternalAgent
Allow: /

# Scrapers puros sin beneficio para el negocio
User-agent: CCBot
Disallow: /
User-agent: Bytespider
Disallow: /

Sitemap: https://{dominio}/sitemap-index.xml
```

Notas: (1) no bloquees `/css/`, `/js/`, `/img/` (Google necesita renderizar); (2) si Cloudflare antepone su managed robots.txt, tu archivo queda debajo y **gana el bloqueo de Cloudflare** para esos agentes: revisá con `curl https://{dominio}/robots.txt` después de activar el proxy; (3) el `Disallow: /*?utm_` es para evitar rastreo de duplicados, no reemplaza el canonical.

### GA4: `click_wsp` como key event y cómo llevarlo a Ads / GSC

- [OFICIAL, terminología] En GA4, desde marzo 2024, las "conversions" se llaman **key events**; se marcan en Admin → Events → toggle "Mark as key event" (Google Analytics Help, https://support.google.com/analytics/answer/9267568) [posiblemente desactualizado: no pude abrir la página en esta sesión, pero la terminología no cambió en 2025-2026].
- Implementación mínima en la plantilla (sin GTM):

```html
<a href="https://wa.me/{telefono}?text=Hola,%20necesito%20{servicio}%20en%20{zona}"
   class="cta-wsp" data-servicio="{servicio}" data-zona="{zona}" rel="noopener" target="_blank">WhatsApp</a>
<script>
document.addEventListener('click', function (e) {
  var a = e.target.closest('a.cta-wsp'); if (!a) return;
  gtag('event', 'click_wsp', {
    servicio: a.dataset.servicio, zona: a.dataset.zona,
    page_location: location.href, transport_type: 'beacon'
  });
});
</script>
```

- Después: (1) en GA4 marcar `click_wsp` como **key event**; (2) registrar `servicio` y `zona` como **custom dimensions** (event-scoped) para ver leads por página; (3) **Google Ads**: vincular GA4 ↔ Ads y en Ads → Goals → Conversions → Import → GA4 properties → Web, importar `click_wsp` como acción de conversión (secundario, `acaprino/daodan` 2026; coincide con el flujo oficial). Si el cliente hace Ads, esa importación es lo que permite pujar por conversiones.
- **Search Console no recibe eventos**: GSC no tiene conversiones. Lo que hacés es cruzar en Looker Studio (o en GA4 con la integración de Search Console) impresiones/clics por página con `click_wsp` por página. Alternativa barata: exportar GA4 → BigQuery (free tier) y unir por `page_location`.
- Tip: usar un `?text=` prellenado con servicio y zona te sirve doble: el cliente sabe de qué página vino y vos podés contar leads reales aunque el usuario no vuelva.

---

## 9. Hosting y geolocalización

- [OFICIAL] Google, "Managing multi-regional and multilingual sites" — https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites (espejo 2026-06-08). Señales de país, textual:
  - ccTLD: "tied to a specific country (for example .de for Germany, .cn for China), and therefore provide a strong signal to both users and search engines that your site is explicitly intended for a certain country."
  - hreflang: "whether in tags, headers, or sitemaps".
  - Server location (IP): "The server location is often physically near your users and can be a signal about your site's intended audience. Some websites use distributed content delivery networks (CDNs) or are hosted in a country with better webserver infrastructure, so it is not a definitive signal."
  - Otras: "local addresses and phone numbers on the pages, the use of local language and currency, links from other local sites, or signals from your Business Profile (where available)."
  - gTLD (.com, .net, .org…): "aren't associated with specific locations"; hay que fijar el objetivo por otros medios.
- [OFICIAL] La herramienta **International Targeting de Search Console fue retirada en 2022**: ya no podés elegir país para un .com desde GSC (secundario, claude-seo hreflang 2026). Para un .com que apunta a UY o AR, las palancas son: hreflang `es-UY`/`es-AR` (solo si hay versiones), dirección/teléfono locales (+598/+54), moneda, enlaces locales, GBP.
- **Para Benja:** `.uy` para Uruguay y `.com.ar` para Argentina es la opción con menos fricción (señal fuerte, sin configuración). Un `.com` único con `/uy/` y `/ar/` funciona pero exige hreflang bien hecho y contenido realmente distinto (precios, teléfonos, zonas). La IP del servidor **casi no importa**: hostear en San Pablo, Virginia o Frankfurt detrás de Cloudflare es indistinguible para Google; lo que importa de la ubicación es la latencia (TTFB → LCP), por eso conviene un edge/CDN con PoP en Buenos Aires/São Paulo. Bing sí da algo más de peso a IP y `content-language` [OPINIÓN, secundario].

---

## Plantillas JSON-LD

Variables: `{nombre}`, `{url}` (home sin barra final), `{telefono}` (E.164, ej. +59899123456), `{servicio}`, `{servicio_slug}`, `{zona}`, `{zona_slug}`, `{departamento}`, `{tipo}` (de la tabla nicho → @type), `{direccion…}`, `{lat}`, `{lng}`.

### A. Home — LocalBusiness (+ WebSite)

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": ["{tipo}", "LocalBusiness"],
      "@id": "{url}/#negocio",
      "name": "{nombre}",
      "url": "{url}/",
      "telephone": "{telefono}",
      "image": ["{url}/img/frente-local.webp", "{url}/img/equipo.webp"],
      "logo": "{url}/img/logo.png",
      "description": "{nombre}: {servicio} en {departamento}. Presupuesto por WhatsApp, atención en el día.",
      "priceRange": "$$",
      "currenciesAccepted": "UYU",
      "paymentAccepted": "Efectivo, transferencia, tarjeta",
      "address": {
        "@type": "PostalAddress",
        "streetAddress": "{calle_y_numero}",
        "addressLocality": "{ciudad}",
        "addressRegion": "{departamento}",
        "postalCode": "{cp}",
        "addressCountry": "UY"
      },
      "geo": { "@type": "GeoCoordinates", "latitude": {lat}, "longitude": {lng} },
      "areaServed": [
        { "@type": "AdministrativeArea", "name": "{departamento}" },
        { "@type": "City", "name": "{zona_1}" },
        { "@type": "City", "name": "{zona_2}" },
        { "@type": "GeoCircle",
          "geoMidpoint": { "@type": "GeoCoordinates", "latitude": {lat}, "longitude": {lng} },
          "geoRadius": "30000" }
      ],
      "openingHoursSpecification": [{
        "@type": "OpeningHoursSpecification",
        "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"],
        "opens": "00:00", "closes": "23:59"
      }],
      "contactPoint": [{
        "@type": "ContactPoint",
        "contactType": "customer service",
        "telephone": "{telefono}",
        "url": "https://wa.me/{telefono_sin_mas}",
        "availableLanguage": "es",
        "areaServed": "UY"
      }],
      "sameAs": ["https://www.instagram.com/{cuenta}", "https://www.facebook.com/{cuenta}"],
      "knowsAbout": ["{servicio}", "{servicio_2}", "{servicio_3}"],
      "hasOfferCatalog": {
        "@type": "OfferCatalog",
        "name": "Servicios",
        "itemListElement": [
          { "@type": "Offer", "itemOffered": { "@type": "Service", "@id": "{url}/{servicio_slug}/#servicio", "name": "{servicio}" } },
          { "@type": "Offer", "itemOffered": { "@type": "Service", "@id": "{url}/{servicio_2_slug}/#servicio", "name": "{servicio_2}" } }
        ]
      }
    },
    {
      "@type": "WebSite",
      "@id": "{url}/#website",
      "url": "{url}/",
      "name": "{nombre}",
      "publisher": { "@id": "{url}/#negocio" },
      "inLanguage": "es-UY"
    }
  ]
}
```

Notas: `["{tipo}","LocalBusiness"]` cubre validadores estrictos; para AR: `addressCountry: "AR"`, `currenciesAccepted: "ARS"`, `inLanguage: "es-AR"`. Sin `aggregateRating`/`review`.

### B. Página servicio × zona — Service + provider LocalBusiness + BreadcrumbList (+ WebPage)

```json
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Service",
      "@id": "{url}/{servicio_slug}/{zona_slug}/#servicio",
      "name": "{servicio} en {zona}",
      "serviceType": "{servicio}",
      "description": "{servicio} en {zona}, {departamento}. Llegamos en {tiempo} minutos. Presupuesto sin cargo por WhatsApp.",
      "provider": { "@id": "{url}/#negocio" },
      "areaServed": {
        "@type": "City",
        "name": "{zona}",
        "containedInPlace": { "@type": "AdministrativeArea", "name": "{departamento}" }
      },
      "availableChannel": {
        "@type": "ServiceChannel",
        "serviceUrl": "https://wa.me/{telefono_sin_mas}?text=Hola,%20necesito%20{servicio_urlencoded}%20en%20{zona_urlencoded}",
        "servicePhone": { "@type": "ContactPoint", "telephone": "{telefono}", "contactType": "customer service" },
        "availableLanguage": "es"
      },
      "offers": {
        "@type": "Offer",
        "priceCurrency": "UYU",
        "price": "{precio_desde}",
        "priceSpecification": { "@type": "PriceSpecification", "minPrice": "{precio_desde}", "priceCurrency": "UYU" },
        "availability": "https://schema.org/InStock",
        "areaServed": { "@type": "City", "name": "{zona}" }
      },
      "image": "{url}/img/{servicio_slug}-real.webp",
      "potentialAction": {
        "@type": "CommunicateAction",
        "name": "Escribir por WhatsApp",
        "target": {
          "@type": "EntryPoint",
          "urlTemplate": "https://wa.me/{telefono_sin_mas}?text=Hola,%20necesito%20{servicio_urlencoded}%20en%20{zona_urlencoded}",
          "actionPlatform": ["https://schema.org/MobileWebPlatform", "https://schema.org/DesktopWebPlatform"]
        }
      }
    },
    {
      "@type": "BreadcrumbList",
      "@id": "{url}/{servicio_slug}/{zona_slug}/#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Inicio", "item": "{url}/" },
        { "@type": "ListItem", "position": 2, "name": "{servicio}", "item": "{url}/{servicio_slug}/" },
        { "@type": "ListItem", "position": 3, "name": "{departamento}", "item": "{url}/{servicio_slug}/{departamento_slug}/" },
        { "@type": "ListItem", "position": 4, "name": "{zona}" }
      ]
    },
    {
      "@type": "WebPage",
      "@id": "{url}/{servicio_slug}/{zona_slug}/",
      "url": "{url}/{servicio_slug}/{zona_slug}/",
      "name": "{servicio} en {zona} | {nombre}",
      "isPartOf": { "@id": "{url}/#website" },
      "about": { "@id": "{url}/{servicio_slug}/{zona_slug}/#servicio" },
      "breadcrumb": { "@id": "{url}/{servicio_slug}/{zona_slug}/#breadcrumb" },
      "inLanguage": "es-UY"
    }
  ]
}
```

Notas: (1) el `provider` por `@id` apunta al LocalBusiness de la home: **no repitas** un LocalBusiness completo con dirección inventada en cada zona (Google: "Fully-qualified URL of the specific business location" — la ubicación es una sola). (2) Si el precio no es fijo, eliminá `offers` en vez de poner "0". (3) `Service` no genera rich result; el breadcrumb sí. (4) El breadcrumb visible en HTML debe ser idéntico.

### C. FAQPage (opcional, contenido visible obligatorio)

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "@id": "{url}/{servicio_slug}/{zona_slug}/#faq",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "¿Cuánto tarda en llegar un {profesional} a {zona}?",
      "acceptedAnswer": { "@type": "Answer", "text": "Entre {tiempo_min} y {tiempo_max} minutos según la hora. Escribinos por WhatsApp al {telefono} y te confirmamos el tiempo real." }
    },
    {
      "@type": "Question",
      "name": "¿Cuánto cuesta {servicio} en {zona}?",
      "acceptedAnswer": { "@type": "Answer", "text": "Desde ${precio_desde} UYU. El presupuesto es sin cargo y lo pasamos por WhatsApp con foto del trabajo." }
    },
    {
      "@type": "Question",
      "name": "¿Atienden urgencias de {servicio} de noche o fines de semana en {zona}?",
      "acceptedAnswer": { "@type": "Answer", "text": "{respuesta_real_del_negocio}" }
    }
  ]
}
```

Notas: desde 2026-05-07 no produce rich result en Google; se mantiene solo si las FAQ están visibles y son distintas por página (Google: "Mark up only one instance of repetitive FAQ content across your site"). Si tus FAQ son idénticas en 300 zonas, **no** las marques en todas.

---

## Implicancias para Benja

1. **Técnico mínimo = performance aburrida**: HTML cacheado, hero sin lazy con `fetchpriority`, dimensiones en todas las imágenes, un solo script de analítica, mapa por click. Con CrUX en verde no hay más puntos que ganar; el ranking se decide por contenido y señales locales (GBP, reseñas, enlaces).
2. **Indexación**: sitemaps segmentados por tipo + `lastmod` real por página + IndexNow (Bing/Copilot) + enlazado interno. **Nada de Indexing API** para páginas de servicio (texto oficial restrictivo, Googlers advirtiendo 2025, riesgo de revocación). "Solicitar indexación" solo para 5-10 páginas clave al lanzar.
3. **Schema**: un LocalBusiness con subtipo exacto (tabla) y `@id` en la home; en cada zona `Service` + `provider @id` + `areaServed City` + `BreadcrumbList`. **Sin estrellas propias**. Sin `ProfessionalService`. `Service`/`areaServed`/`knowsAbout` son semánticos: no esperes que muevan nada; el breadcrumb y la validación limpia son lo que se ve.
4. **FAQ**: contenido visible sí (sirve a usuarios y a LLM), JSON-LD opcional y solo cuando las preguntas son distintas por página.
5. **Imágenes IA**: solo ilustraciones; nunca "obra realizada", "equipo" ni "local". Pedí fotos reales al cliente (10-15 de celular). Alt honesto, IPTC `trainedAlgorithmicMedia` en las IA.
6. **Enlazado**: hub servicio → departamento → barrio; vecinos geográficos reales (tabla de adyacencias); servicio↔servicio relevante; enlaces en el cuerpo; sin mega-footer; HTML sitemap de zonas; cero huérfanas; auditoría mensual de profundidad ≤3 y entrantes ≥3.
7. **Doorway es el riesgo real**: cientos de páginas iguales cambiando el barrio es literalmente el ejemplo de Google. Cada zona tiene que tener algo que solo aplique ahí (tiempo de llegada, casos, referencias, precios, FAQ locales). Si no lo tenés, menos páginas y mejores.
8. **robots.txt**: permitir buscadores y asistentes; permitir o no entrenamiento es decisión de negocio sin efecto en visibilidad; revisar que Cloudflare no te antepone bloqueos. Olvidate de llms.txt.
9. **Medición**: `click_wsp` como key event con `servicio`/`zona` como dimensiones; importar a Ads si hay campañas; cruzar con GSC en Looker Studio.
10. **Dominios**: `.uy` y `.com.ar` separados, sin hreflang. IP del servidor irrelevante; CDN con PoP regional por latencia. Para un `.com` único: hreflang `es-UY`/`es-AR` + señales locales (GSC ya no permite elegir país).

## Contradicciones encontradas

1. **"CWV es factor de ranking" vs "es un tiebreaker"**: Google dice que sus sistemas "look to reward" buena experiencia pero "always seeks to show the most relevant content, even if the page experience is sub-par" [OFICIAL]. Terceros lo llaman tiebreaker [OPINIÓN]. **Aplicar:** llegar a verde en CrUX y no invertir más.
2. **FAQPage: "solo gov/salud" (2023) vs "retirado para todos" (2026)**: el mismo doc de Google contiene ambas frases; la de 2026-05-07 manda. Terceros dicen que "sigue ayudando a AI Mode" [OPINIÓN] contra el test de Ahrefs 2026 (sin uplift) y Google (no hace falta schema para IA). **Aplicar:** FAQ visible sí, JSON-LD opcional.
3. **Schema y citas en IA**: la industria GEO recomienda "schema para LLM"; Google (guía 2026-07-10) dice no sobreinvertir y Ahrefs no midió uplift. **Aplicar:** lo mínimo correcto y validado; el esfuerzo va a contenido y entidades consistentes (NAP, GBP).
4. **Indexing API "funciona para todo"** (foros, herramientas de "rapid indexing") vs texto oficial (solo JobPosting/BroadcastEvent) + Mueller 2025 ("spammers misuse") + Illyes (revocación). **Aplicar:** no usarla.
5. **Bloquear Google-Extended "te saca de AI Overviews"** (mito frecuente) vs doc oficial (no afecta inclusión ni ranking; AIO se controla con nosnippet/max-snippet). **Aplicar:** decidir Google-Extended solo por la política de entrenamiento.
6. **ChatGPT usa Bing** (varias fuentes 2026) vs OpenAI (documenta su propio OAI-SearchBot, no menciona Bing). **Aplicar:** permitir OAI-SearchBot **y** hacer IndexNow/Bing Webmaster; cubre ambos escenarios.
7. **Servidor/IP importa** (agencias) vs Google ("not a definitive signal", CDNs lo diluyen). **Aplicar:** elegir hosting por latencia y precio, no por país.
8. **"Máximo 100 enlaces por página"** (folklore) vs Google 2026 ("if you think it's too much, then it probably is") y Zyppy (rendimiento decreciente pasados ~45-50 entrantes). **Aplicar:** 10-20 enlaces internos en cuerpo por página zona, sin mega-footer.
9. **Mostrar reseñas de Google con estrellas en el sitio** (plugins) vs guía de review snippet (self-serving → inelegible; acción manual posible). **Aplicar:** mostrar texto/enlace, sin `Review`/`AggregateRating`.
10. **Imágenes IA "penalizan"** (mitos) vs Google (no hay política; Illyes: "no direct") y QRG (penaliza el engaño/falta de esfuerzo, no la herramienta). **Aplicar:** IA para ilustrar, nunca para probar; fotos reales para lo que vende.

## Fuentes principales (URL original — cómo se accedió)

- schema.org vocabulario oficial: https://github.com/schemaorg/schemaorg (releases 29.2 parseada; `versions.json`: 30.1 del 2026-09-16) — leído 2026-09-24.
- Google Search Central (espejo `bsisduck/google-search-ads-analytics-docs`, scrape 2026-06-08): core-web-vitals, page-experience, build-sitemap, large-site-managing-crawl-budget, ask-google-to-recrawl, local-business, sd-policies, search-gallery, faqpage, breadcrumb, review-snippet, image-license-metadata, google-images, lazy-loading, links-crawlable, consolidate-duplicate-urls, using-gen-ai-content, spam-policies, ai-features, managing-multi-regional-sites, localized-versions, job-posting.
- Google Indexing API quickstart / using-api (2026-07-16) — citado vía `harlan-zw/requestindexing.com` y `johnkorzhuk/grabient` (2026-08).
- Google AI optimization guide (2026-05-15 / 2026-07-10) — vía `AgriciDaniel/claude-seo` (2026-09-23).
- Google Search Central updates (FAQ 2026-05-07) — vía `AgriciDaniel/claude-seo` data/google-updates.json.
- GoogleChrome/web-vitals README (v5) — leído 2026-09-24.
- Anthropic crawlers: https://support.claude.com/en/articles/8896518 — leído directo 2026-09-24.
- OpenAI bots: https://developers.openai.com/api/docs/bots — vía `rybbit-io/rybbit` (2026-09-13).
- Perplexity bots: https://docs.perplexity.ai/guides/bots — vía rybbit (2026-09-13).
- Cloudflare, "Block AI bots" (defaults 2026-09-15) — repo oficial `cloudflare/cloudflare-docs`, leído 2026-09-24.
- ai.robots.txt (tabla de bots) — leído 2026-09-24.
- C2PA specifications (v2.4) — repo oficial, leído 2026-09-24.
- IndexNow FAQ / searchengines.json — vía grabient (verificado 2026-08-16).
- Ahrefs, schema vs citas IA — https://ahrefs.com/blog/schema-ai-citations/ (2026-05-11) vía espejo `0xenzyme/awesome-seo-articles`.
- Zyppy internal links study — https://zyppy.com/seo/internal-links/seo-study/ vía `youtube-jono/seo-agent` (2026).
- Mobile-first final: https://developers.google.com/search/blog/2024/06/mobile-indexing-vlast-final-final vía `MariusYvard/NullToHero` (2026).
- QRG 2025-01-23 y 2025-09-11 — citas secundarias (`claude-seo`, `Yahya-Halim/Websites`), PDF no abierto.
