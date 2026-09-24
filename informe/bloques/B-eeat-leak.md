# BLOQUE B — E-E-A-T y cómo Google decide quién es el experto

**Para:** Benja (Montevideo) — sitios de servicios locales UY/AR (cerrajería, mudanzas, electricistas, yeso, aire acondicionado, casas contenedores), rank and rent con EMD (cerrajero.uy, yesocaba.com), sitios de nicho de un solo servicio.
**Fecha de investigación:** 24 de septiembre de 2026.

## Nota metodológica (leer antes de usar)

- **Etiquetas:** `[OFICIAL]` (Google Search Central, Sullivan, Mueller, Illyes, QRG, Ayuda de GBP) · `[FILTRACIÓN/PATENTE]` · `[TEST]` (estudios con datos) · `[OPINIÓN]` (analistas/agencias) · `[posiblemente desactualizado]` cuando el único respaldo es viejo · `[NO VERIFICADO EN SESIÓN]` cuando el texto literal lo reconstruyo de mi conocimiento del documento y no pude abrir la fuente.
- **Limitación grave de esta sesión:** el proxy de red del entorno bloqueó **todas** las aperturas de página (WebFetch) que intenté: developers.google.com, static.googleusercontent.com, guidelines.raterhub.com, services.google.com, seroundtable.com, searchengineland.com, searchenginejournal.com, ipullrank.com, sparktoro.com, patents.google.com, hobo-web.co.uk, whitespark.ca, amsive.com, semrush.com, justice.gov, kopp-online-marketing.com, seo-kreativ.de, localdominator.co, pravinkumar.co, cdn.contentpowered.com; web.archive.org y r.jina.ai tampoco estaban disponibles. Además, después de 26 búsquedas el presupuesto de WebSearch de la sesión (compartido) llegó a 200/200 y se agotó.
- **Consecuencia:** los hallazgos salen de (a) los resúmenes y snippets de 26 búsquedas web distintas (inglés y español) y (b) mi conocimiento directo de los documentos (QRG, página de contenido útil, patente, leak, juicio DOJ), con corte de conocimiento junio 2026. **Ninguna cita literal fue cotejada contra el PDF/página original en esta sesión.** Donde reproduzco texto literal lo marco como `[NO VERIFICADO EN SESIÓN]`. Antes de publicar cualquier cosa con comillas, abrir la fuente y confirmar.
- Lo que sí es sólido: la estructura de los documentos, las fechas de versión, los nombres de atributos del leak y las conclusiones de los análisis citados, porque coinciden entre múltiples resultados de búsqueda independientes.

---

## 1. Search Quality Rater Guidelines (QRG): versión vigente y señales concretas para un negocio de servicios local

### 1.1 Qué versión está vigente y qué cambió

- `[OFICIAL]` **Versión vigente: 11 de septiembre de 2025 (182 páginas).** Reemplazó a la del 23 de enero de 2025 (181 págs.). Google la calificó de "minor update": pequeñas aclaraciones sobre cómo calificar contenido YMYL y ejemplos nuevos para calificar AI Overviews; "no changes to the overall guidance". Fuente: Search Engine Roundtable, 12/09/2025 — https://www.seroundtable.com/google-search-quality-raters-guidelines-update-40092.html ; Search Engine Land, 09/2025 — https://searchengineland.com/google-updates-search-quality-raters-guidelines-adding-ai-overview-examples-ymyl-definitions-461908 ; PDF oficial: https://guidelines.raterhub.com/searchqualityevaluatorguidelines.pdf (título indexado: "General Guidelines September 11, 2025").
- `[OFICIAL]` **Cambio de enero 2025 (23/01/2025):** el changelog dice, en esencia: alineó las secciones Lowest y Low de Page Quality con las políticas de spam de Google Search; amplió la guía para evaluar interpretaciones e intenciones menores en Needs Met; cambios menores (rangos de rating, ejemplos viejos eliminados, typos, requisitos de navegador). Además: la sección 2.1 "Important Definitions" incorporó una definición de contenido generado con IA generativa, y se agregó al Lowest la frase de que "la calificación Lowest es obligatoria si la página fue creada para beneficiar al dueño del sitio (p. ej., ganar dinero) con muy poco o ningún intento de beneficiar a los visitantes". Fuente: Search Engine Land, 01/2025 — https://searchengineland.com/google-updates-search-quality-raters-guidelines-with-a-focus-on-spam-451073 ; Search Engine Journal — https://www.searchenginejournal.com/googles-updated-raters-guidelines-refines-concept-of-low-quality/545766/ ; PPC Land — https://ppc.land/google-updates-quality-rater-guidelines-with-ai-content-evaluation-criteria/ ; copia del PDF de enero 2025: https://cdn.contentpowered.com/wp-content/uploads/2025/02/searchqualityevaluatorguidelines.pdf
- `[OFICIAL]` **Septiembre 2025 – YMYL:** la definición de YMYL se aclaró y se agregó explícitamente información cívica (procedimientos de votación, contenido que afecta la confianza en instituciones) dentro de la categoría "Society/Government". Fuente: seo-kreativ.de (análisis de 182 págs.), 09/2025 — https://www.seo-kreativ.de/en/blog/google-quality-raters-update_9-25/ ; en español: Diego Hidalgo, "Quality Rater Guidelines de Septiembre 2025" — https://diegohidalgolopez.com/seo/quality-rater-guidelines-de-septiembre-2025/
- `[OPINIÓN — PROBABLE FABRICACIÓN]` Un solo sitio (pravinkumar.co) afirma que hubo una "actualización de junio 2026" con una "sección 5.2" que castiga resúmenes de IA sin autor, una "5.4 Verifiable Real World Expertise" y un flag "Synthetic Authority" en "6.1". **No aparece en Search Engine Roundtable ni en Search Engine Land**, que cubren cada cambio del PDF, y varias fuentes de 2026 (dageno.ai, theguidex.com, hmdigitalsolution.com) dicen que la versión de septiembre 2025 sigue siendo la vigente "a mediados de 2026". Los números de sección tampoco coinciden con la estructura real del documento (la 5.x es "Low quality", no existe un "flag" en 6.1). **Tratar como inventado hasta ver el changelog en el PDF.** URL: https://www.pravinkumar.co/blog/google-june-2026-quality-rater-guidelines-webflow-aeo-2026 (no se pudo abrir).
- `[OFICIAL]` Aclaración de fondo, repetida en el propio QRG y en el overview público de Google: las calificaciones de los raters **no afectan directamente el ranking** de una página; se usan para evaluar y entrenar cambios de los sistemas. Fuente: overview oficial "Search Quality Rater Guidelines: An Overview" — https://services.google.com/fh/files/misc/hsw-sqrg.pdf ; ver también la página "Creating helpful content" (punto 2).

### 1.2 Estructura del documento que importa para una página de servicio (numeración de la versión 2025)

`[OFICIAL] [NO VERIFICADO EN SESIÓN]` — numeración y contenido reconstruidos del PDF de 2025; verificar página exacta antes de citar.

| Sección | Qué dice (esencia) | Por qué le importa a Benja |
|---|---|---|
| 2.3 Your Money or Your Life (YMYL) | Temas que pueden afectar salud, seguridad, estabilidad financiera o bienestar; se evalúa "en un espectro": *clear YMYL* / *may be YMYL* / *not or unlikely YMYL*. Categorías: Health or Safety, Financial Security, Society (incl. cívica desde 09/2025), Other. | Define cuánto E-E-A-T se le exige a cerrajero/electricista (ver 1.4). |
| 2.5.3 Finding Who is Responsible for the Website and Who Created the Content on the Page | El rater debe identificar quién (persona, empresa) es responsable del sitio y quién creó el contenido. "Most websites have 'contact us' or 'about us'..." Para tiendas y sitios con transacciones se exige información de atención al cliente clara y satisfactoria. | La página "Sobre nosotros" + contacto real es lo primero que mira un rater. |
| 3.3 Reputation of the Website and Content Creators (3.3.1–3.3.4) | Investigación de reputación **fuera del sitio**: reseñas, referencias, recomendaciones de expertos, noticias, Wikipedia, BBB. Para negocios pequeños: la falta de información de reputación **no** es señal de baja calidad; muchas reseñas negativas sobre estafa/servicio sí lo son. | Las reseñas en Google Maps y foros son "la reputación" del cerrajero; no hace falta prensa, pero no puede haber acusaciones de estafa. |
| 3.4 Experience, Expertise, Authoritativeness, and Trust (E-E-A-T) | Definiciones (ver 1.3). "Trust is the most important member of the E-E-A-T family". 3.4.1: para YMYL, cuándo alcanza Experience y cuándo hace falta Expertise formal. | Es la sección madre. |
| 4.0–4.6 Lowest Quality Pages | 4.5 Untrustworthy pages: 4.5.1 *Inadequate information about the website or content creator for the purpose of the page*; 4.5.2 *Lowest E-E-A-T*; 4.5.3 *Deceptive page purpose, deceptive information about the website, deceptive design* (tabla de ejemplos ampliada en 2025); 4.5.4 MC obstruido; 4.5.5 comportamiento malicioso. 4.6 Spammy webpages alineado con las políticas de spam (expired domain abuse, site reputation abuse, scaled content abuse, etc.). | Un sitio que **oculta quién es** o **finge ser un negocio que no existe** cae en 4.5.1/4.5.3 = Lowest. |
| 5.0–5.x Low Quality Pages | Low por: E-E-A-T inadecuado para el propósito, MC de baja calidad/esfuerzo, información insuficiente sobre el sitio/creador, **información exagerada o levemente engañosa sobre el sitio o el creador** (agregado enero 2025), reputación levemente negativa, título/páginas engañosas, anuncios que distraen. | "20 años de experiencia" inventados o credenciales de marketing → Low. |
| 6.0 Medium | Nada malo pero nada destacable. | Es donde cae la mayoría de los sitios de servicios genéricos. |
| 7.0 High / 8.0 Highest | High: MC de alta calidad, alto nivel de E-E-A-T, reputación positiva. Highest: "very high level of E-E-A-T", MC de muy alta calidad con esfuerzo, originalidad, talento o habilidad evidente, reputación muy positiva. | Para un cerrajero: fotos propias, trabajo real documentado, reseñas verificables. |
| Parte 2 (Needs Met) + secciones de "Visit-in-Person" / ubicación del usuario | Consultas con intención de ir/llamar: el rater considera la ubicación; una página de negocio local con dirección, horario, teléfono y servicios claros puede ser "Fully Meets" para la consulta local. | Explica por qué la página de servicio + ciudad con NAP completo "cumple". |

### 1.3 Definiciones literales de E-E-A-T (sección 3.4)

`[OFICIAL] [NO VERIFICADO EN SESIÓN — literal reconstruido; coincide con lo citado por SEL 12/2022 y por múltiples resúmenes 2025-2026]`

- **Experience:** "Consider the extent to which the content creator has the necessary first-hand or life experience for the topic."
- **Expertise:** "Consider the extent to which the content creator has the necessary knowledge or skill for the topic."
- **Authoritativeness:** "Consider the extent to which the content creator or the website is known as a go-to source for the topic."
- **Trust:** "Consider the extent to which the page is accurate, honest, safe, and reliable."
- **La frase clave:** "Trust is the most important member of the E-E-A-T family because untrustworthy pages have low E-E-A-T no matter how Experienced, Expert, or Authoritative they may seem." Confirmada por búsqueda: Search Engine Land 12/2022 — https://searchengineland.com/google-search-quality-rater-guidelines-changes-december-2022-390350 ; Search Engine Roundtable 12/2022 — https://www.seroundtable.com/google-e-e-a-t-experience-search-quality-raters-guidelines-34576.html ; guía 2026 de seo-kreativ — https://www.seo-kreativ.de/en/blog/e-e-a-t-guide-for-more-trust-and-top-rankings/
- El QRG agrega que el tipo de E-E-A-T necesario **depende del tipo de página**: "Online stores need secure online payment systems and reliable customer service"; para consejos de salud se exige expertise formal; para relatos personales alcanza la experiencia. También dice que "everyday expertise" (pericia cotidiana) es válida: alguien que hace el trabajo todos los días es experto aunque no tenga título. `[NO VERIFICADO EN SESIÓN]`

### 1.4 ¿Un cerrajero o un electricista es YMYL?

- `[OFICIAL]` El QRG **no nombra** cerrajeros, electricistas, mudanzas ni yeso. La búsqueda confirmó que las categorías son Health or Safety, Financial Security, Society/Government (con cívica desde 09/2025) y que "YMYL only applies to queries with the potential to do harm". Fuente: Search Engine Land guía YMYL — https://searchengineland.com/guide/ymyl ; seroundtable 09/2025 (arriba); overview oficial https://services.google.com/fh/files/misc/hsw-sqrg.pdf
- `[OFICIAL] [NO VERIFICADO EN SESIÓN]` El QRG evalúa YMYL en espectro con una tabla de ejemplos (clear / may be / not). Ejemplos del tipo "comprar un auto" o "cuándo cambiar el cepillo de dientes" están en *may be YMYL*; "elegir un detergente" o "fondos de pantalla" en *not YMYL*.
- `[OPINIÓN — recomendación para Benja]` Aplicando el espectro:
  - **Cerrajería (urgencias, apertura de puertas):** *may be YMYL* por seguridad del hogar y porque el rubro tiene historial mundial de estafas (precio cambiado en el lugar, "cerrajeros" falsos). Un rater que ve un sitio de cerrajero sin nombre real, sin dirección, sin teléfono verificable, lo asocia a ese patrón → riesgo de Low/Lowest por 4.5.1.
  - **Electricista:** *may be YMYL* (seguridad física, incendios, riesgo eléctrico, habilitaciones UTE/edesur). Si la página da consejos técnicos ("cómo cambiar un tablero"), sube el requisito de Expertise.
  - **Mudanzas:** *may be YMYL* leve por lo financiero (gasto alto, estafas con depósitos). Transparencia de precios/garantías pesa.
  - **Casas contenedores:** *may be YMYL* por Financial Security (compra grande) y por seguridad estructural/habilitación. De todos los rubros, es el que más se acerca a "clear".
  - **Yeso / aire acondicionado (instalación):** *unlikely YMYL* salvo que la página dé instrucciones de seguridad (gas refrigerante, eléctrica).
  - Conclusión: **ninguno es "clear YMYL" como salud o finanzas**, pero cerrajería, electricidad y contenedores están claramente en la zona gris, y ahí el QRG pide más Trust (identidad, contacto, reputación) más que credenciales académicas.

### 1.5 Señales concretas que un rater busca en un negocio de servicios local (síntesis QRG + guías)

`[OFICIAL]` derivado de 2.5.3, 3.3, 3.4, 4.5 y 5.x; `[OPINIÓN]` las aplicaciones a rubro.

1. **Quién es responsable** (2.5.3): nombre del negocio o persona, "Sobre nosotros" con quién hace el trabajo, dirección o zona real, teléfono/WhatsApp que atiende, e-mail. Si el propósito de la página es vender un servicio y no se sabe quién lo presta → 4.5.1 Lowest.
2. **Quién hace el trabajo** (3.4 Experience/Expertise): nombre del técnico o del equipo, años reales, matrícula/habilitación cuando existe (UTE para instaladores eléctricos en Uruguay; matrícula municipal/COPIME o APSE en Argentina para electricistas; habilitación de gasista para aire; registro de transportistas para mudanzas). Un rater no verifica matrículas, pero sí nota si la página "parece" de alguien real.
3. **Fotos reales de trabajos** (3.4 Experience + 7/8 "effort, originality"): fotos propias, con contexto local reconocible (barrio, edificio, tablero, cerradura instalada), no stock. Esto es la evidencia de "first-hand experience" que el QRG define.
4. **Reputación externa** (3.3): reseñas en Google Maps, Facebook, foros; menciones en directorios locales; ausencia de acusaciones de estafa. Para negocios chicos, la falta de reputación no penaliza; la reputación negativa sí.
5. **Precios, garantías, condiciones** (Trust = "accurate, honest, safe, reliable" + 5.x "exaggerated or mildly misleading"): un "desde $X" realista, garantía escrita, qué pasa si algo sale mal, medios de pago. Promesas imposibles ("llegamos en 5 minutos a cualquier punto de Montevideo") son "información exagerada" → Low.
6. **Consistencia con GBP y directorios** (NAP): el rater busca al negocio fuera del sitio; si el nombre/teléfono no coinciden, baja el Trust.
7. **Propósito claro y no engañoso** (4.5.3): que la página no simule ser un negocio distinto al que atiende (relevante en rank and rent, ver punto 7).

---

## 2. "Creating helpful, reliable, people-first content" — preguntas Who / How / Why y aplicación a una página de servicio

`[OFICIAL]` URL: https://developers.google.com/search/docs/fundamentals/creating-helpful-content (no se pudo abrir en esta sesión; texto `[NO VERIFICADO EN SESIÓN]`, reconstruido del documento; las preguntas centrales fueron confirmadas por snippets de búsqueda de digitalhitmen.com.au, seoworks.co.uk, expresswriters.com, victorious.com, ethanlazuk.com 2026).

### 2.1 Preguntas de autoevaluación (Content and quality questions)

- Does the content provide original information, reporting, research, or analysis? *(confirmado por snippet)*
- Does the content provide a substantial, complete, or comprehensive description of the topic?
- Does the content provide insightful analysis or interesting information that is beyond the obvious?
- If the content draws on other sources, does it avoid simply copying or rewriting those sources, and instead provide substantial additional value and originality? *(confirmado por snippet)*
- Does the main heading or page title provide a descriptive, helpful summary of the content?
- Does the main heading or page title avoid exaggerating or being shocking in nature?
- Is this the sort of page you'd want to bookmark, share with a friend, or recommend?
- Would you expect to see this content in or referenced by a printed magazine, encyclopedia, or book?
- Does the content provide substantial value when compared to other pages in search results?
- Does the content have any spelling or stylistic issues?
- Is the content produced well, or does it appear sloppy or hastily produced?
- Is the content mass-produced by or outsourced to a large number of creators, or spread across a large network of sites, so that individual pages or sites don't get as much attention or care?

### 2.2 Expertise questions

- Does the content present information in a way that makes you want to trust it, such as clear sourcing, evidence of the expertise involved, background about the author or the site that publishes it, such as through links to an author page or a site's About page? *(confirmado por snippet)*
- If you researched the site producing the content, would you come away with an impression that it is well-trusted or widely-recognized as an authority on its topic?
- Is this content written or reviewed by an expert or enthusiast who demonstrably knows the topic well?
- Does the content have any easily-verified factual errors?

### 2.3 People-first vs. search-engine-first

- Focus on people-first content: "Do you have an existing or intended audience for your business or site that would find the content useful if they came directly to you?" · "Does your content clearly demonstrate first-hand expertise and a depth of knowledge (for example, expertise that comes from having actually used a product or service, or visiting a place)?" *(confirmado por snippet)* · "Does your site have a primary purpose or focus?" · "After reading your content, will someone leave feeling they've learned enough about a topic to help achieve their goal?" · "Will someone reading your content leave feeling like they've had a satisfying experience?"
- Avoid search engine-first: "Is the content primarily made to attract visits from search engines?" · "Are you producing lots of content on many different topics in hopes that some of it might perform well?" · "Are you using extensive automation to produce content on many topics?" · "Are you mainly summarizing what others have to say without adding much value?" · "Does your content leave readers feeling like they need to search again to get better information from other sources?" · "Are you writing to a particular word count...? (No, we don't.)" · "Did you decide to enter some niche topic area without any real expertise, but instead mainly because you thought you'd get search traffic?" · "Are you changing the date of pages to make them seem fresh when the content has not substantially changed?"

### 2.4 Sección E-E-A-T de la página (literal esencial)

- "Google's automated systems are designed to use many different factors to rank great content. After identifying relevant content, our systems aim to prioritize those that seem most helpful. To do this, they identify a mix of factors that can help determine which content demonstrates aspects of experience, expertise, authoritativeness, and trustworthiness, or what we call E-E-A-T." · "Of these aspects, trust is most important." · "E-E-A-T itself isn't a specific ranking factor, but using a mix of factors that can identify content with good E-E-A-T is useful." · Sobre raters: "their feedback doesn't directly influence ranking".

### 2.5 "Ask Who, How, and Why about your content" (literal esencial)

- **Who (who created the content):** "Something that helps people intuitively understand the E-E-A-T of content is when it's clear who created it." Preguntas: "Is it self-evident to your visitors who authored your content?" · "Do pages carry a byline, where one might be expected?" · "Do bylines lead to further information about the author or authors involved, giving background about them and the areas they write about?"
- **How (how the content was created):** "It's helpful to readers to know how a piece of content was produced." Ejemplo del propio documento: en reseñas de productos, contar cuántos productos se probaron, qué tests se hicieron, y mostrar evidencia (fotos propias) de la experiencia. Preguntas: "Is the use of automation, including AI-generation, self-evident to visitors through disclosures or in other ways?" · "Are you providing background about how automation or AI-generation was used to create content?" · "Are you explaining why automation or AI was seen as useful to produce content?"
- **Why (why was the content created):** "'Why' is perhaps the most important question to answer about your content." · "The 'why' should be that you're creating content primarily to help people, content that is useful to visitors if they come to your site directly." · "If the 'why' is that you're primarily making content to attract search engine visits, that's not aligned with what our systems seek to reward."

### 2.6 Cómo se traduce a una página de servicio (aplicación) `[OPINIÓN]`

| Pregunta de Google | Página de servicio de Benja |
|---|---|
| Who | Bloque "Quién te atiende": nombre del cerrajero/electricista, foto real, zona, años, matrícula. En rank and rent: el **operador actual**, no un personaje. |
| How | "Cómo trabajamos": pasos del servicio, herramientas, tiempos reales, fotos del proceso en obras locales, qué incluye el presupuesto. Si el texto se redactó con IA, no hace falta banner, pero sí que la información específica (precios, zonas, casos) venga del operador. |
| Why | La página existe para que alguien de Pocitos con la puerta trabada resuelva; no para "rankear cerrajero montevideo". Test: ¿la página sirve igual si el usuario llega por WhatsApp sin pasar por Google? |
| Original information | Precios orientativos reales del mercado local, tiempos de llegada por zona, marcas de cerraduras comunes en edificios de Montevideo, requisitos de UTE/edesur, trámites de habilitación para contenedores en la intendencia. Eso no lo tiene el top 10 genérico. |
| Search-engine-first | Evitar 30 páginas "cerrajero + barrio" con el mismo texto; evitar "niche topic area without any real expertise" — el sitio de nicho de un solo servicio está **bien alineado** con "Does your site have a primary purpose or focus?" siempre que el contenido sea específico. |

---

## 3. E-E-A-T para páginas de servicio local: hallazgos 2025–2026 con datos

- `[TEST]` **Whitespark Local Search Ranking Factors 2026** (publicado nov. 2025; 47 expertos, 187 factores; nueva categoría "AI Search visibility impact"). Peso estimado para Local Pack: GBP 32 %, on-page 19 %, reseñas 16 %, links 15 %, comportamiento 8 %, citaciones 7 %, personalización 3 %. "Los mayores cambios para 2026 son la mayor importancia de las señales de reseñas y de comportamiento"; la categoría primaria de GBP sigue como factor individual n.º 1. URL: https://whitespark.ca/local-search-ranking-factors/ ; resumen: https://www.soci.ai/blog/local-memo-local-ranking-factors-of-2026-have-arrived/ ; https://streetfightmag.com/2025/11/13/streets-ahead-whitespark-local-ranking-factors-and-local-lists-in-gbp/ (no pude abrir el reporte; el desglose de local organic no lo pude confirmar).
- `[TEST]` **Sterling Sky (Joy Hawkins), 2025:** "We Analyzed 8,186 Businesses in 200 Cities. Here's What Actually Gets You Ranking for 'Near Me' in 2025" — https://www.sterlingsky.ca/what-gets-you-ranking-for-near-me-2025/ ; y "The State of Local SEO in 2026" — https://www.sterlingsky.ca/the-state-of-local-seo-in-2026/ . No pude abrir los datos; se citan como fuentes a revisar. No encontré un estudio de Sterling Sky específicamente sobre E-E-A-T en webs de servicios.
- `[TEST]` **Ahrefs 2025, 75.000 marcas:** las menciones de marca en la web (aunque no tengan link) fueron la variable con mayor correlación con visibilidad en respuestas de IA, por encima de los backlinks. Citado en https://www.dreamhost.com/blog/eeat-for-small-businesses/ y en varios artículos 2025-2026 (estudio original de Ahrefs no abierto).
- `[TEST]` **Lily Ray / Amsive, core update de diciembre 2025** (anunciado 11/12/2025, 18 días de rollout, terminó 29/12/2025): Wikipedia el mayor perdedor (−435 puntos de visibilidad), caídas en grandes editores de salud, medios y plataformas sociales; e-commerce y retail entre los ganadores. Lectura de Ray: el foco de 2025 fue **intención del usuario y si el resultado cumple expectativas**, más que "señales de autor". URL: https://www.amsive.com/insights/seo/googles-december-2025-core-update-winners-losers-analysis/ ; LinkedIn 12/2025: https://www.linkedin.com/posts/lily-ray-44755615_googles-december-2025-core-update-winners-activity-7417610562257260545-mg35 ; junio 2025: https://www.linkedin.com/posts/lily-ray-44755615_june-2025-core-update-winners-losers-activity-7356023706571223040-7cjs . Google hizo 4 core updates en 2025 (marzo, junio, agosto, diciembre).
- `[OFICIAL]` **Google Ayuda GBP "Tips to improve your local ranking":** los tres factores son Relevance, Distance, Prominence. Prominence "is also based on information that Google has about a business from across the web, like links, articles and directories. Google review count and review score factor into local search ranking... Your position in web results is also a factor, so SEO best practices apply." URL: https://support.google.com/business/answer/7091?hl=en (vigente 2025).
- `[OFICIAL]` **Danny Sullivan, enero 2024 (vigente):** Google **no verifica bylines ni credenciales**; los bylines no son factor de ranking directo; "E-E-A-T is not a ranking factor" (no hay un "score"). Google usa señales proxy para identificar contenido que *un humano* juzgaría con buen E-E-A-T. "Having an expert write things doesn't magically make you rank better because anyone could self-declare someone to be an expert." Fuentes: https://www.pageonepower.com/linkarati/google-doesnt-check-bylines-according-to-google-liason ; https://blogmanagement.io/blog/e-e-a-t-is-not-a-ranking-factor ; https://www.relevantaudience.com/seo/do-author-bylines-matter-for-seo/ (2026); https://www.searchenginejournal.com/googles-danny-sullivan-presentation/501558/
- `[OPINIÓN]` **Marie Haynes (2025):** lee los documentos del DOJ como prueba de que los sistemas de Google priorizan **satisfacción del usuario** (clics largos, no volver a buscar) por encima de "optimización vectorial", y que E-E-A-T son "señales que Google puede usar para determinar autenticidad". Fuentes: https://opportunityandauthority.com/2025/07/04/marie-haynes-seo-through-quality-trust-e-e-a-t-opportunity-authority/ ; https://searchengineland.com/topic/marie-haynes
- `[OPINIÓN]` Guías 2026 de E-E-A-T local (localdominator.co, theadfirm.net, localmighty.com, sievesoftech.com, sproutsagesolutions.com) coinciden en la misma lista, sin datos propios: Experience = fotos de trabajos terminados, casos, descripciones de proyectos; Expertise = licencias/matrículas, técnicos con nombre; Authority = menciones locales, directorios, volumen de reseñas; Trust = NAP consistente, GBP verificado, reseñas auténticas, HTTPS. URLs: https://localdominator.co/eeat-for-local-seo/ ; https://www.localmighty.com/blog/e-e-a-t-seo-local-businesses/ ; https://www.theadfirm.net/e-e-a-t-for-local-businesses-what-it-means-and-how-to-build-it
- `[OPINIÓN]` Guías de rubro (electricistas/cerrajeros 2026): mostrar número de matrícula específico "que la competencia omitió", citar normas (en EE. UU. el NEC; equivalente local: reglamento de UTE / AEA 90364 en Argentina), páginas de área de servicio con señales de que realmente se atiende ese barrio; 83 % de consumidores usa Google para reseñas locales; recencia y respuesta a reseñas afectan confianza. URLs: https://comradeweb.com/blog/locksmith-seo/ ; https://www.servicetitan.com/blog/electrician-seo ; https://hardlabormarketing.com/blog/local-seo-strategies-electrical-contractors-2026/
- `[OPINIÓN – español]` Marketinhouse (2025) y Cyberclick (2025) resumen el giro 2025 del QRG: "la confianza es el factor clave", contenido con IA aceptado si aporta valor, "las evaluaciones de los raters no influyen directamente pero ajustan algoritmos". URLs: https://www.marketinhouse.es/como-mejorar-el-eeat-en-2025-nuevas-directrices-de-los-quality-raters-de-google/ ; https://www.cyberclick.es/numerical-blog/las-nuevas-directrices-de-google-para-2025-que-significan-para-el-contenido-generado-con-ia ; https://seo.pe/nuevas-directrices-evaluadores-calidad/
- `[OPINIÓN – sin respaldo]` Afirmaciones tipo "en 2026 Google convirtió a E-E-A-T en una de las señales de ranking más fuertes para todo lo comercial" (sievesoftech, seoscore.tools "15 signals Google actually checks") **no tienen fuente oficial**; contradicen a Sullivan (no hay score). Usar solo como checklist, no como "cómo funciona Google".

---

## 4. Patente de Information Gain

### 4.1 Datos duros

- `[FILTRACIÓN/PATENTE]` **"Contextual estimation of link information gain"** — Google LLC. Publicación de solicitud **US 2020/0349181 A1** (no 0349179); patente concedida **US 11,354,342 B2** (7 de junio de 2022); continuaciones **US 11,720,613 B2** (2023) y **US 12,013,887 B2** (junio 2024); hay una publicación posterior (12,326,889). Inventores: Victor Carbune, Pedro Gonnet Anders (y coinventores). Presentada 2018. URLs: https://patents.google.com/patent/US11354342B2/en ; https://patents.google.com/patent/US20200349181A1/en ; https://patents.google.com/patent/US12013887B2/en ; PDF USPTO: https://image-ppubs.uspto.gov/dirsearch-public/print/downloadPdf/12013887
- `[FILTRACIÓN/PATENTE] [NO VERIFICADO EN SESIÓN — abstract reconstruido]` Abstract (esencia): "An information gain score for a given document is indicative of additional information that is included in the document beyond information contained in documents that were previously viewed by the user... the information gain score may be determined for one or more documents by applying data from the documents across a machine learning model... Based on the information gain scores of a set of documents, the documents can be provided to the user in a manner that reflects the likely information gain that can be attained by the user if the user were to view the documents." (Confirmado casi literal por snippet de Semrush y SEJ.)

### 4.2 Qué mide realmente (y la contradicción con cómo lo usa la industria)

- `[FILTRACIÓN/PATENTE]` La patente mide **ganancia de información relativa a lo que el usuario ya vio** (documentos previos en la sesión / conversación con asistente), usando un modelo ML sobre representaciones de los documentos; y describe **reordenar o presentar** documentos según esa ganancia, actualizando dinámicamente con la interacción del usuario. Fuentes: SEJ (Roger Montti), "Google's Information Gain Patent for Ranking Web Pages" — https://www.searchenginejournal.com/googles-information-gain-patent-for-ranking-web-pages/524464/ ; Semrush, "What Is Information Gain in SEO & Does Google Measure It?" — https://www.semrush.com/blog/information-gain/ ; explicación de Olaf Kopp: https://www.kopp-online-marketing.com/information-gain-how-it-is-calculated-which-factors-are-crucial y https://www.scribd.com/document/937441606/Contextual-estimation-of-link-information-gain-Olaf-Kopp-Explanation
- `[OPINIÓN]` La industria (Clearscope, Searchbloom, SEO.com, NEURONwriter, outpaceseo 2026) la reinterpretó como "cuánta información nueva aporta tu página respecto al **top 10 / corpus**". Es una extrapolación razonable pero **no es lo que dice la patente**, y Google nunca confirmó que la use en ranking web. Semrush lo dice explícito: "It's unclear whether Google uses information gain as described in its patent." URLs: https://www.clearscope.io/blog/information-gain-seo ; https://www.searchbloom.com/blog/information-gain-seo/ ; https://www.seo.com/blog/information-gain/ ; https://searchengineland.com/what-is-information-gain-seo-why-it-matters-429763
- `[OPINIÓN – sin respaldo, descartar]` "Information Gain: Google's #1 Ranking Signal in 2026 (April)" (digitalapplied.com) afirma que el core update de marzo 2026 "operacionalizó" la señal a escala; no cita fuente oficial. Otros posts hablan de "5-to-7 rule" y "vector shift". Tratar como marketing.
- `[OPINIÓN]` Dato que sí circula con números (Searchbloom/SEO.com 2025-2026): citas directas de un experto en primera persona → "400 % de lift" promedio en visibilidad en AI Mode/AI Overviews/Copilot. Es un estudio de agencia, sin metodología pública abierta en esta sesión → tratar como indicio, no como prueba.

### 4.3 Cómo aplicarlo a una página de servicio (aunque Google no lo use tal cual, el ejercicio sirve porque coincide con "original information" del punto 2) `[OPINIÓN]`

1. Abrir el top 10 para "cerrajero montevideo" / "electricista caba" y listar qué dicen todos: 24 hs, urgencias, "profesionales", "precios accesibles". Eso tiene ganancia de información **cero**.
2. Escribir lo que ninguno tiene y que el operador sabe por hacer el trabajo:
   - Tabla de precios orientativos por tipo de trabajo y franja horaria (día/noche/feriado), en pesos, con fecha.
   - Tiempos reales de llegada por zona (Centro/Cordón 20', Carrasco 40', etc.).
   - Qué cerraduras/tableros/equipos son los más comunes en edificios de la ciudad y qué repuestos se consiguen.
   - Requisitos legales locales: UTE para instalaciones eléctricas, gasista matriculado para split con gas, trámite municipal para casas contenedores (permiso de construcción, zonificación), documentación para mudanzas interdepartamentales.
   - Casos reales con fotos propias: "apertura de puerta blindada en Pocitos, 35 min, sin daños".
   - Errores frecuentes que ve el técnico (cerraduras mal instaladas, tableros sin disyuntor) y cómo evitar estafas del rubro.
3. Para AI Overviews / AI Mode: frases atribuibles a una persona real ("según Martín, cerrajero con 12 años en Montevideo: ...") con nombre, foto y contacto.
4. Métrica interna: por cada página de servicio, listar ≥5 datos que no aparecen en el top 10. Si no hay 5, la página no tiene ganancia de información.

---

## 5. Leak del Content Warehouse (mayo 2024) y atributos relevantes para sitios de nicho con EMD

`[FILTRACIÓN/PATENTE]` **Advertencia obligatoria:** son **atributos de una API de documentación interna** (2.596 módulos, 14.014 atributos) — describen qué datos Google almacena, **no** su peso, ni si están activos, ni si son factores de ranking. Google confirmó la autenticidad el 4 de junio de 2024 y advirtió: "We would caution against making inaccurate assumptions about Search based on out-of-context, outdated, or incomplete information." `[NO VERIFICADO EN SESIÓN]` Fuentes primarias: Rand Fishkin (SparkToro), 27/05/2024 — https://sparktoro.com/blog/an-anonymous-source-shared-thousands-of-leaked-google-search-api-documents-with-me-everyone-in-seo-should-see-them/ ; Mike King (iPullRank), 28/05/2024 — https://ipullrank.com/google-algo-leak ; SEL 05/2024 — https://searchengineland.com/unpacking-googles-massive-search-documentation-leak-442716 ; Hobo (Shaun Anderson, análisis 2024-2025) — https://www.hobo-web.co.uk/the-google-content-warehouse-leak-2024/ y https://www.hobo-web.co.uk/compressedqualitysignals/ ; navboost.com (2025) — https://navboost.com/google-api-leak/

### 5.1 Atributos y qué implicarían para un sitio de un solo servicio con EMD

| Atributo (módulo) | Qué dice la documentación | Lectura para Benja |
|---|---|---|
| **siteAuthority** (QualityNsrNsrData) | Señal de calidad a nivel dominio que influye en las páginas del dominio; contradice el "no usamos domain authority". Análisis 2025: "influye en cuán rápido pueden rankear páginas de un dominio para términos competitivos". | Un EMD nuevo empieza con siteAuthority bajo; se construye con links, menciones y comportamiento, no con el nombre del dominio. |
| **siteFocusScore** y **siteRadius** (QualityAuthorityTopicEmbeddings, siteEmbeddings) | siteFocusScore: cuánto está enfocado el sitio en un tema; siteRadius: cuánto se desvían los embeddings de cada página del embedding del sitio. | **Favorable al sitio de nicho de un solo servicio**: cerrajero.uy con 100 % de páginas sobre cerrajería tiene focus alto y radius bajo. Meterle "mudanzas" o "yeso" al mismo dominio ensancha el radius. Argumento a favor de un dominio por servicio. |
| **NavBoost / CrapsClickSignals**: goodClicks, badClicks, lastLongestClicks, unsquashedClicks, squashedClicks; ventana de 13 meses; segmentado por país/dispositivo; datos de Chrome (chromeInTotal) | Almacena clics por query y documento; "lastLongestClicks" = el último clic largo de la sesión (el que resolvió). Función de "squashing" para normalizar. | En local, el "último clic largo" es el que termina en llamada/WhatsApp. Una página que el usuario abre y abandona (badClick) para llamar al siguiente resultado pierde. |
| **chard**, **tofu**, **keto** (NsrData) | "Site-level chard score: site quality predictor based on content"; tofu y keto son predictores de calidad de sitio análogos, basados en contenido (interpretación de Hobo: "sustancia" del contenido). | Predictores de calidad **a nivel sitio** calculados sobre el contenido: un sitio de 6 páginas genéricas puntúa bajo aunque el dominio sea exacto. |
| **contentEffort** (QualityNsrPQData) | "LLM-based effort estimation for article pages" — un modelo estima el esfuerzo invertido. | Coincide con QRG 7/8 ("effort, originality, talent or skill"). Fotos propias, tablas, datos locales = esfuerzo detectable. `[NO VERIFICADO EN SESIÓN]` |
| **hostAge** (PerDocData) | "The earliest firstseen date of all pages in this host/domain... used in twiddler to sandbox fresh spam in serving time." | Existe un sandbox, pero **para spam fresco**, no para toda web nueva. Un EMD recién registrado con contenido masivo y links comprados encaja en "fresh spam". Un EMD nuevo con GBP real y contenido específico, no necesariamente. |
| **smallPersonalSite** (NsrData) | "Score of small personal site promotion" (go/promoting-personal-blogs-v1). No está claro si promueve o demota ni si está activo. | Un sitio de servicios comercial **no es** "personal site"; no contar con esto. |
| **titlematchScore** (NsrData) | "Site-level title match score": qué tan bien los títulos del sitio coinciden con las queries. | Los titles con "cerrajero + ciudad" siguen importando; es a nivel sitio, así que la coherencia de titles en todo el dominio suma. |
| **OriginalContentScore** (PerDocData) | Score de originalidad, especialmente relevante para páginas con poco contenido (rango 0–512, tope 127 en páginas cortas según análisis). | Las páginas de servicio suelen ser cortas → la originalidad pesa más que el largo. Texto spineado entre 10 páginas de barrio = score bajo. |
| **exactMatchDomainDemotion** (CompressedQualitySignals) | Democión para EMD de baja calidad; implementación del EMD update de 2012. | El EMD no da bonus; **da un demote si el sitio es de baja calidad**. cerrajero.uy solo vale si la calidad acompaña. |
| **babyPandaDemotion / babyPandaV2Demotion**, **navDemotion**, **anchorMismatchDemotion**, **serpDemotion**, **lowQuality** | Familia de demotes: HCU ("baby Panda"), mala navegación, anchors que no coinciden, demote por comportamiento en SERP. | Redes de sitios clonados con anchors "cerrajero X" idénticos → anchorMismatch y HCU-style demotion. |
| **LocalWWWInfo**: address, brickAndMortarStrength, geotopicality, isLargeChain, isLargeLocalwwwinfo; **localityScore** (NsrData) | Información local del sitio: dirección detectada, "fuerza" de presencia física, geotopicalidad (geo del contenido independiente del negocio), cadena grande o no. | Google intenta entender **si el sitio pertenece a un negocio físico real y dónde**. Un sitio sin dirección ni entidad asociada tiene brickAndMortarStrength baja. Sumar dirección (o zona precisa), LocalBusiness schema, mapa, GBP enlazado. |
| **isAuthor / authorObfuscatedGaia**, entidades de autor | Google intenta asociar contenido a entidades de autor. | Relevante si Benja crea "autores" falsos: la entidad no existe fuera del sitio. |
| **Twiddlers** | Re-rankers posteriores al ranking principal (freshness, diversidad, sandbox, demotes). | Muchas de las demotes anteriores se aplican como twiddlers en serving. |

Fuentes por atributo: iPullRank (siteAuthority, NavBoost, Chrome, twiddlers, hostAge, exactMatchDomainDemotion, babyPanda); SparkToro (siteAuthority, NavBoost, whitelists, small sites); Hobo/CompressedQualitySignals (demotions, chard/tofu/keto, NSR); Growfusely — https://growfusely.com/blog/google-api-leak/ ; Vizion — https://www.vizion.com/blog/everything-you-need-to-know-about-the-google-leak-misstatements-and-api-revelations/ ; Mojo Dojo — https://mojodojo.io/blog/googleapi-content-warehouse-leak-an-ongoing-analysis ; Missing Intent "Google NSR and Q*" — https://missingintent.com/google-nsr ; Jussi Hyvärinen (LocalWWWInfo) — https://jussihyvarinen.com/unveiling-googles-algorithm-secrets-what-the-leaked-api-documents-reveal-about-ranking-factors/ ; searchlogistics — https://www.searchlogistics.com/learn/seo/algorithm/google-search-leak/ ; Hawk Web Marketing "what we know now in 2025" — https://www.hawkwebmarketing.com/google-search-apis-2024-documentation-leak-what-we-know-now-in-2025/

### 5.2 Síntesis para sitios de nicho con EMD `[OPINIÓN sobre base FILTRACIÓN]`

- **A favor:** siteFocusScore/siteRadius premian el foco; titlematchScore premia titles alineados; localityScore/LocalWWWInfo premian tener entidad local reconocible.
- **En contra:** exactMatchDomainDemotion + hostAge sandbox + chard/tofu/contentEffort bajos castigan justo el patrón "EMD nuevo + 6 páginas genéricas + sin entidad". siteAuthority parte de cero.
- **Neutral/ignorar:** smallPersonalSite.
- Lo que el leak **no** dice: pesos, umbrales, si está activo hoy (2026). Todo esto es evidencia de qué **guarda** Google, no de cómo rankea.

---

## 6. Juicio DOJ vs. Google (2023–2025): lo que se reveló sobre señales

- `[OFICIAL – testimonio bajo juramento]` **Pandu Nayak (VP Search), octubre 2023:** NavBoost existe desde 2005; usa **13 meses** de datos de clics (antes 18); es "one of the important signals"; Google tiene "over 100 raw signals" que se combinan; los clics se segmentan por localización y dispositivo. Fuentes: SEL "How Google Search and ranking works, according to Google's Pandu Nayak" (10/2023) — https://searchengineland.com/how-google-search-ranking-works-pandu-nayak-435395 ; navboost.com — https://navboost.com/google-antitrust-trial/ ; Hobo — https://www.hobo-web.co.uk/navboost-how-google-uses-large-scale-user-interaction-data-to-rank-websites/
- `[OFICIAL – exhibit del juicio]` **"Los tres pilares" (documento interno "Logging & Ranking"):** Body = "what the document says about itself"; Anchors = "what the web says about the document"; User interactions = "what users say about the document" (clics, scrolls, hovers, atención). Fuente: Search Engine Roundtable, 11/2023 — https://www.seroundtable.com/google-3-pillars-of-ranking-36340.html
- `[OFICIAL – exhibits]` **"ABC signals" y T\*/Q\*:** artículo de SEL (02/2024) con presentaciones de ingenieros de Google (Eric Lehman, HJ Kim, Pandu Nayak): Topicality (T\*) combina A (Anchors), B (Body), C (Clicks); Q\* es la señal de calidad de sitio, "largely static" y en gran parte independiente de la query; Navboost, RankBrain, DeepRank, RankEmbedBERT y "freshness" son señales adicionales; Google aún depende de "hand-crafted signals" ajustables por ingenieros; frase de Lehman (2018): "we do not understand documents. We fake it." Fuente: https://searchengineland.com/google-abc-ranking-signals-455360 ; Hobo — https://www.hobo-web.co.uk/google-vs-doj/ y https://www.hobo-web.co.uk/how-google-works/
- `[OFICIAL – opinión del juez, 5/08/2024 y documentos de remedios 2025]` **RankEmbed / RankEmbedBERT:** modelo dual-encoder que embebe query y documento; entrenado con **70 días de logs de búsqueda + scores de quality raters**; Nayak confirmó que mejoró mucho las consultas long-tail/infrecuentes. **Glue:** contraparte de NavBoost para features de "universal search" (local pack, imágenes, videos, knowledge panels); **Instant Glue** agrega las mismas señales de interacción de las últimas 24 h con ~10 min de latencia. **Tangram (ex Tetris):** arma el layout final de la SERP. Fuentes: Hobo "How Google Works in 2025" ; searchengineworld — https://www.searchengineworld.com/fresh-doc-dump-pagerank-navboost-and-rankembed-doj-papers-outline-googles-stack ; xpert.digital — https://xpert.digital/en/newly-revealed-google-ranking/ ; DOJ — https://www.justice.gov/atr/media/1398866/dl (no abierto)
- `[OFICIAL – remedios]` **Fallo de remedios (juez Mehta, 2 de septiembre de 2025):** Google debe compartir con "Qualified Competitors", a costo marginal y periódicamente, partes del índice y los "User-side Data" usados para construir/operar los modelos **Glue** (y datos relacionados con NavBoost/RankEmbed según el texto de remedios). Fuentes: Medianama 09/2025 — https://www.medianama.com/2025/09/223-us-court-google-share-search-data-rivals-doj-antitrust-case/ ; Hobo DOJ 2020-2025 (arriba).
- `[OFICIAL – exhibits]` **Quality raters:** las calificaciones (IS scores) se usan como **datos de entrenamiento/evaluación** de modelos como RankEmbedBERT, no como voto directo sobre un sitio. Fuente: Hobo "How human quality raters are used" — https://www.hobo-web.co.uk/how-human-quality-raters-are-used-new-evidence-from-doj-v-google-antitrust-trial/ ; Olaf Kopp, "What we can learn from DOJ trial and API leak" — https://www.kopp-online-marketing.com/what-we-can-learn-from-doj-trial-and-api-leak-for-seo
- `[OPINIÓN]` Lectura consensuada 2025 (Kopp, Haynes, Hobo): la "calidad" en Google es en gran parte **Q\* (sitio, estático) + comportamiento (NavBoost/Glue) + modelos entrenados con raters**. E-E-A-T no es un score, pero los raters que califican con el QRG **entrenan** los modelos que sí puntúan. Por eso el QRG describe el objetivo, y las señales de clic miden si se cumplió.

### 6.1 Implicancia directa para páginas de servicio local `[OPINIÓN]`

- Para queries locales, el usuario decide en segundos: el "clic largo" o la llamada es la señal. Página lenta, sin teléfono arriba, sin precio orientativo → badClick.
- Glue rankea el **local pack** con interacción: llamadas, direcciones, clics al sitio desde GBP. GBP y web se retroalimentan.
- Q\* es a nivel sitio y "casi estático": un sitio nuevo de 6 páginas no lo mueve rápido; se mueve con tiempo, links/menciones reales y comportamiento sostenido (13 meses de ventana).

---

## 7. E-E-A-T en rank and rent cuando el operador cambia: viable vs. riesgoso

### 7.1 Qué dice Google (políticas vigentes)

- `[OFICIAL]` **GBP:** "Lead generation agents or companies aren't eligible for a Business Profile"; el perfil debe pertenecer al negocio que atiende al cliente; los negocios deben tener contacto en persona con clientes (o ser SAB legítimos); reseñas falsas/incentivadas prohibidas; keyword stuffing en el nombre y reseñas falsas se detectan más rápido en 2025; perfiles no verificados se eliminan a los 60 días de inactividad. Google eliminó 20 M+ perfiles falsos (2022) y bloqueó/eliminó 115 M+ reseñas (2023). Fuentes: https://support.google.com/business/answer/13762416?hl=en ; https://birdeye.com/blog/google-business-profile-guidelines/ (2026) ; https://professorm.org/google-my-business/gmb-suspension/google-business-profile-guidelines-and-rules/ ; hilo oficial de la comunidad sobre rank and rent con GBP ficticios: https://support.google.com/business/thread/337646525
- `[OFICIAL]` **QRG 4.5.3 / 4.5.1:** página que engaña sobre quién es responsable o sobre su propósito → Lowest; información exagerada o levemente engañosa sobre el sitio o el creador → Low (agregado 01/2025). Ver punto 1.
- `[OFICIAL]` **Políticas de spam** alineadas con QRG desde 01/2025: expired domain abuse, site reputation abuse, scaled content abuse, doorway pages. Redes de sitios-ciudad con el mismo texto = doorway/scaled content. `[NO VERIFICADO EN SESIÓN — política pública de Google Search Central]`
- `[OFICIAL] [posiblemente desactualizado]` **Reseñas en tu propio sitio con schema:** desde 09/2019 Google no muestra rich results de reseñas "self-serving" (reseñas del propio negocio marcadas con LocalBusiness/Organization). Se pueden mostrar testimonios, pero no esperar estrellas en SERP, y las fabricadas son "deceptive" bajo QRG. `[NO VERIFICADO EN SESIÓN]`
- `[OFICIAL – regulatorio, EE. UU.]` FTC Consumer Review Rule (vigente desde oct. 2024): multas hasta US$ 53.088 por violación por reseñas falsas/pagadas/suprimidas; primeras cartas de advertencia en dic. 2025. En UY/AR no aplica la FTC, pero **las políticas de Google son globales** y en Argentina la publicidad engañosa está alcanzada por la Ley de Defensa del Consumidor y Lealtad Comercial; en Uruguay por la Ley 17.250. Fuentes: https://www.lawfuel.com/what-google-reviews-for-businesses-look-like-under-active-ftc-enforcement/ ; https://wiserreview.com/blog/google-review-policy/ (2026) ; https://birdeye.com/blog/google-review-policy/ (2026)
- `[OPINIÓN – foro especializado]` Local Search Forum (2025) describe el patrón típico de rank and rent que Google castiga: "same copy + paste websites, generic stock photos, and tons of fake AI reviews" con GBP que pertenecen al rentista. URL: https://localsearchforum.com/threads/what-kind-of-ranking-scam-is-this.62894/

### 7.2 Matriz viable / riesgoso `[OPINIÓN sobre base OFICIAL]`

| Práctica | Viabilidad | Por qué |
|---|---|---|
| Sitio con **marca propia** ("Cerrajero.uy — red de cerrajeros verificados") que dice explícitamente que deriva el pedido a un profesional asociado, con el operador actual nombrado en la página | **Viable** | El "quién es responsable" es honesto (2.5.3); el propósito es claro (4.5.3). Es un modelo de marketplace/derivación, no un engaño. |
| Bloque "Quién te atiende" con nombre real, foto real, matrícula y zona del operador vigente; se reemplaza cuando cambia el operador (con fecha de actualización) | **Viable** | Es la forma concreta de "Who"; Google no verifica credenciales pero el rater y el usuario sí notan personas reales. |
| Fotos de trabajos reales del operador actual (pedir 10–20 fotos por mes como parte del contrato) | **Viable, clave** | Evidencia de Experience; esfuerzo detectable (contentEffort/OriginalContentScore). |
| Reseñas: pedir al operador que dirija a sus clientes a **su** GBP; en el sitio mostrar testimonios con nombre + fecha + tipo de trabajo, sin schema de estrellas | **Viable** | Reseñas reales en propiedad del negocio real. |
| GBP a nombre del rentista o con dirección ficticia, mismo teléfono rotando entre operadores | **Riesgoso / prohibido** | Viola elegibilidad de GBP (lead gen no elegible); suspensión y contagio al sitio. |
| **Autor/técnico inventado** con foto stock o generada por IA y "20 años de experiencia" | **Riesgoso** | QRG 4.5.3 "deceptive information about the website"; 5.x "exaggerated or mildly misleading"; entidad inexistente fuera del sitio (isAuthor sin respaldo). Sullivan: los bylines no rankean; el falso no ayuda y sí expone. |
| **Fotos stock** de cerrajero/electricista en la página de servicio | **Riesgo medio** | No es una violación, pero el rater lo cuenta como cero Experience y cero esfuerzo; y contradice "How". Usar solo como fondo, nunca como "nuestro equipo". |
| **Reseñas fabricadas** (en el sitio o en GBP) | **Riesgoso / prohibido** | Política de Maps UGC; QRG deceptive; detección ML 2025; en AR/UY publicidad engañosa. |
| Clonar el mismo sitio en 10 dominios/ciudades con texto spineado | **Riesgoso** | Scaled content/doorway; anchorMismatch/babyPanda demotions; OriginalContentScore bajo. |
| Cambiar de operador y **no actualizar** "Sobre nosotros", fotos y matrícula | **Riesgo medio** | Se vuelve "deceptive information about the website"; la reputación externa (reseñas del operador anterior) deja de coincidir. |
| Texto redactado con IA a partir de datos del operador (precios, zonas, casos) | **Viable** | Google acepta IA si el contenido es útil y original (QRG 2.1 2025; página de contenido útil). El riesgo es la IA sin datos propios. |

### 7.3 Protocolo práctico de "E-E-A-T transferible" para rank and rent `[OPINIÓN]`

1. La **marca es del sitio** (Cerrajero.uy), la **experiencia es del operador**. Separar en la página: "Cerrajero.uy conecta con cerrajeros verificados en Montevideo. Hoy atiende: [Nombre], matrícula/registro [n.º], zona [x]."
2. Página "Cómo verificamos a los cerrajeros/electricistas": criterios reales (matrícula, antigüedad, seguro, reseñas). Eso es E-E-A-T de la **plataforma**, que no cambia con el operador.
3. Contrato con el operador: fotos mensuales, 3 casos por mes con 4 líneas, permiso de usar nombre y foto, reseñas a su GBP, y aviso de baja para actualizar la web el mismo día.
4. Nunca GBP falsos; si Benja quiere pack, el GBP es del operador y enlaza al sitio (o el sitio es la web oficial del operador durante el contrato, con acuerdo escrito).
5. Dejar rastro de actualización: "Última actualización de precios: septiembre 2026" real.

---

## Implicancias para Benja

### Confirmado (con respaldo OFICIAL o testimonio)

- Trust manda: identidad clara, contacto real, propósito honesto. Sin eso, un rater califica Lowest/Low aunque el contenido sea bueno (QRG 2.5.3, 3.4, 4.5, 5.x).
- E-E-A-T **no es un score** ni Google verifica credenciales (Sullivan 2024); lo que sí existe son señales de calidad de sitio (Q\*, siteAuthority/NSR) y de comportamiento (NavBoost/Glue, 13 meses), y modelos entrenados con raters. Traducción: hacé que la página *parezca y sea* de un profesional real, y que resuelva rápido (llamada/WhatsApp), porque eso es lo que se mide.
- La versión vigente del QRG es la del 11/09/2025; no hay evidencia sólida de una versión 2026. Los cambios 2025 relevantes: Lowest para páginas hechas solo para beneficiar al dueño, Low por información exagerada sobre el sitio/creador, alineación con políticas de spam.
- El sitio de nicho de un solo servicio está alineado con "Does your site have a primary purpose or focus?" y con siteFocusScore/siteRadius (leak). El foco es un activo.
- GBP para lead-gen/rentista no es elegible; reseñas falsas prohibidas y cada vez más detectadas.
- Local pack: relevancia, distancia, prominencia (links, artículos, directorios, cantidad y puntaje de reseñas, posición orgánica).

### En riesgo (prácticas actuales típicas de rank and rent)

- EMD nuevo + pocas páginas genéricas + sin entidad local: coincide con exactMatchDomainDemotion, hostAge "fresh spam" sandbox, chard/tofu/contentEffort bajos (leak; atributos, no factores confirmados) y con "search-engine-first" de la página oficial.
- Fotos stock y "equipo" sin nombre: cero Experience para un rater; "How" sin responder.
- Autores o testimonios inventados: Lowest por engaño; expuestos además a normas de publicidad engañosa.
- Sitios clonados por ciudad: scaled content/doorway; OriginalContentScore bajo en páginas cortas.
- Cambio de operador sin actualizar identidad: información engañosa sobre el sitio.

### Falta (para cerrar el bloque con fuentes primarias abiertas)

- Cotejar las citas literales del QRG (3.4, 2.5.3, 4.5.1–4.5.3, 5.x, tabla YMYL de 2.3) contra el PDF de septiembre 2025: https://guidelines.raterhub.com/searchqualityevaluatorguidelines.pdf
- Cotejar las preguntas Who/How/Why y las listas de autoevaluación contra https://developers.google.com/search/docs/fundamentals/creating-helpful-content
- Leer el abstract y la reivindicación 1 de US 11,354,342 B2 en patents.google.com para citar literal.
- Abrir el desglose de "local organic" de Whitespark 2026 y el estudio "near me" de Sterling Sky 2025 (8.186 negocios) para extraer números.
- Verificar la política de reseñas "self-serving" en Search Central (vigencia 2026) y la política de "site reputation abuse"/"scaled content abuse" tal como están hoy.
- Verificar si hubo core updates en 2026 (marzo/mayo) y qué dijo Google; un resultado mencionó un "core update del 21 de mayo de 2026" sin fuente oficial.

---

## Contradicciones encontradas

1. **"E-E-A-T no es factor de ranking" (Sullivan, OFICIAL) vs. "E-E-A-T es una de las señales más fuertes en 2026" (agencias, OPINIÓN).** Aplicar la oficial: no existe score de E-E-A-T; existen proxies (calidad de sitio, comportamiento, modelos entrenados con raters). Para Benja: no gastar en "señales de autor" cosméticas; invertir en identidad real, evidencia de trabajo y experiencia de usuario que produzca clics largos y llamadas.
2. **"Domain authority no existe" (Google, histórico) vs. `siteAuthority` en el leak (FILTRACIÓN).** Aplicar: existe una señal de calidad a nivel sitio (también Q\* en el juicio). Para un EMD nuevo, asumir que arranca en cero y se construye.
3. **Patente de Information Gain: "novedad respecto a lo que el usuario ya vio en su sesión" (PATENTE) vs. "novedad respecto al top 10" (industria, OPINIÓN).** Aplicar la lectura de la industria como *heurística editorial* (coincide con "original information" de la página oficial), no como "señal confirmada". Descartar los posts que la llaman "señal n.º 1 de 2026".
4. **"Actualización del QRG de junio 2026" (pravinkumar.co) vs. cobertura de SER/SEL que muestra la de 11/09/2025 como última.** Aplicar: no existe hasta que aparezca en el changelog del PDF.
5. **Leak: `hostAge` sandbox (FILTRACIÓN) vs. Google "no hay sandbox" (OFICIAL, histórico, posiblemente desactualizado).** Aplicar: hay un sandbox **para spam fresco**; un EMD nuevo con GBP real, contenido específico y sin links comprados no debería caer, pero un lanzamiento masivo de EMD clonados sí.
6. **Clics como señal: Google negó por años el uso de CTR (OFICIAL histórico) vs. NavBoost confirmado bajo juramento (OFICIAL 2023) y detallado en el leak.** Aplicar la versión del juicio: el comportamiento post-clic importa, con ventana de 13 meses, segmentado por país/dispositivo.
7. **Whitespark 2026: peso creciente de reseñas y comportamiento (TEST) vs. rank and rent tradicional apoyado en EMD + on-page.** Aplicar Whitespark: sin GBP legítimo y reseñas reales del operador, el techo del sitio de nicho es el orgánico local, no el pack.
8. **`smallPersonalSite`: promoción de sitios pequeños (FILTRACIÓN) vs. quejas 2024-2025 de sitios chicos golpeados por HCU.** Aplicar: no depende de Benja; sus sitios son comerciales, no "personales"; ignorar.
