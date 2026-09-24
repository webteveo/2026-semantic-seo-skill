# BLOQUE F — GEO / AI search: aparecer citado en respuestas de IA
### (AI Overviews, AI Mode, ChatGPT, Perplexity, Gemini, Copilot) — para sitios de servicios locales UY/AR

Fecha de investigación: 24 de septiembre de 2026. Investigador: agente de investigación SEO. Cliente: Benja (Montevideo), sitios de servicios locales (cerrajería, mudanzas, electricistas, casas contenedores) con CTA WhatsApp medido en GA4, schema LocalBusiness y ficha de Google Business Profile (GBP).

---

## 0. Nota de método y límites (leer primero)

- Se hicieron **14 búsquedas web distintas** (en inglés y español). Después de la búsqueda 14 el presupuesto de búsquedas de la sesión se agotó (límite compartido de 200 llamadas por sesión), por lo que las búsquedas planificadas sobre Bing Places/Apple Business Connect, ChatGPT local, Semrush 230k prompts, Aleyda/Kevin Indig, "GEO optimización motores generativos" y "AI Mode default" **no pudieron ejecutarse**. Lo que se dice de esos temas viene de snippets de otras búsquedas o de conocimiento previo (corte junio 2026) y está marcado.
- El proxy de salida de este entorno **bloquea todos los dominios excepto github.com / raw.githubusercontent.com** (arxiv.org, developers.google.com, blog.google, openai.com, pewresearch.org, ahrefs.com, semrush.com, vercel.com, searchengineland.com, searchenginejournal.com, whitespark.ca, etc. devolvieron EGRESS_BLOCKED). Por eso las **fuentes primarias abiertas** (WebFetch OK) son las alojadas en GitHub:
  1. `GEO-Optim/GEO` README (paper Aggarwal et al.) — https://github.com/GEO-Optim/GEO
  2. `GEO-Optim/GEO/src/geo_functions.py` (prompts exactos de cada método GEO)
  3. `GEO-Optim/GEO/src/run_geo.py` (métricas de visibilidad)
  4. `GEO-Optim/GEO/docs/GEO/index.html` (página oficial del paper: abstract, GEO-bench)
  5. `GEO-Optim/GEO/GEO-Bench/leaderboard/*` (constants + leaderboard.jsonl)
  6. `parameterlab/c-seo-bench` README (NeurIPS D&B 2025, arXiv 2506.11097)
  7. `cxcscmu/AutoGEO` README (ICLR 2026, arXiv 2510.11438)
  8. `ai-robots-txt/ai.robots.txt` (table-of-bot-metrics.md, robots.json, robots.txt) — user-agents de crawlers de IA
  9. `AnswerDotAI/llms-txt` (spec oficial de llms.txt)
  10. `MalteBerlin/LLM-Referrer` (lista de referrers de LLMs, mantenida por el CPO de Peec AI)
  11. `snowplow-referer-parser/referer-parser/referers.yml` (categoría "chatbot" con dominios y utm_sources)
  12. `matomo-org/searchengine-and-social-list/SearchEngines.yml` (entradas ChatGPT/Perplexity)
  13. `jianruntech/geo-score`, `Auriti-Labs/geo-optimizer-skill`, `getauracite/geo-benchmarks`, `haofeix/google-aio-characterization` (para el punto 7: qué es humo)
- Todo lo demás se etiqueta además con **[vía snippet]** = dato citado en resultados de búsqueda pero cuya página no se pudo abrir; o **[CONOCIMIENTO PREVIO – verificar]** = memoria del modelo hasta junio 2026. Recomendación: el agente padre (o Benja) debería abrir las URLs marcadas [vía snippet] desde una máquina sin proxy antes de usarlas en un entregable al cliente.

Etiquetas de tipo de evidencia: **[OFICIAL]** (Google/OpenAI/Microsoft/Perplexity/Anthropic), **[PAPER]** (académico revisado), **[TEST]** (estudio con datos), **[FILTRACIÓN/PATENTE]**, **[OPINIÓN]**.

---

## 1. El paper original "GEO: Generative Engine Optimization" (Aggarwal et al., arXiv 2311.09735, KDD 2024) y sus réplicas

### 1.1 Qué es y qué mide
- **[PAPER]** Aggarwal, Murahari, Rajpurohit, Kalyan, Narasimhan, Deshpande (Princeton, IIT Delhi, Georgia Tech, Allen Institute). Preprint nov-2023, v3 jun-2024, publicado en KDD 2024. Página oficial (abierta vía GitHub Pages source): https://github.com/GEO-Optim/GEO/blob/main/docs/GEO/index.html — abstract: "simple GEO strategies improve visibility by up to 40% in experiments on deployed commercial generative engines"; "GEO methods perform better when tailored to target domains; lower-ranked websites benefit more". Fecha del repo: último update 30-oct-2025.
- **[PAPER]** GEO-bench: 10.000 consultas (8K/1K/1K train/val/test), fuentes MS Marco, ORCAS-1, Natural Questions, AllSouls, LIMA, Davinci-Debate, Perplexity.ai Discover, ELI-5 y consultas generadas por GPT-4; 5 fuentes limpias por consulta; 50+ tags. (index.html, abierto.)
- **[PAPER]** Métricas (run_geo.py, abierto): `impression_wordpos_count_simple` = **Position-Adjusted Word Count** (cuántas palabras de la respuesta vienen de tu fuente, ponderado por posición) y **Subjective Impression** (un LLM evalúa relevancia, unicidad, influencia, diversidad, "follow-up"). El motor generativo de referencia fue un pipeline tipo Perplexity con GPT-3.5 (código referencia "gpt"; versión exacta no explícita en el código abierto).

### 1.2 Los 9 métodos y qué hacen realmente (prompts abiertos en geo_functions.py)
| Método | Qué hace el prompt (literal) | Resultado en el paper |
|---|---|---|
| Cite Sources | "incorporate credible source citations… ensure they sound plausible" (¡admite citas inventadas!) | Top-3, ~+30–40% en Position-Adjusted Word Count |
| Quotation Addition | añade citas atribuidas; "even fake and artificial quotes" | Top-3, ~+30–40% |
| Statistics Addition | "positive, compelling statistics (even if hypothetical)" | Top-3, ~+30–40% (mejor en dominios Law & Government) |
| Fluency Optimization | reescribe para fluidez sin cambiar contenido | Mejora intermedia (~+15–30%) |
| Easy-to-Understand | simplifica enunciados | Mejora leve |
| Unique Words | vocabulario raro | Mejora leve |
| Technical Terms | vocabulario técnico | Mejora leve (mejor en debates/consultas técnicas) |
| Authoritative | tono asertivo "this is a more valuable source" | **Sin mejora significativa** en Position-Adjusted Word Count (según lectura de geo-score del paper, abierto) |
| Keyword Stuffing ("seo_optimize") | inserta hasta 10 keywords nuevas | **No funciona**: ligera caída (~-10%) |

- **[PAPER][CONOCIMIENTO PREVIO – verificar cifra exacta]** Los % por método provienen de la Tabla 2 del paper (v3); los rangos anteriores están reconstruidos de memoria y de dos lecturas independientes abiertas (geo-score: "citing sources, adding statistics and quoting experts raise visibility by up to 40%… authoritative tone produced no significant improvement"; geo-optimizer-skill: "Cite Sources: +115%, Statistics: +40%"). **La cifra "+115%" no es el promedio: es el efecto en fuentes que partían en 5.º lugar** ("lower-ranked websites benefit more"). Cuidado con herramientas que la venden como promedio.
- **[OPINIÓN]** Crítica metodológica (blckalpaca.at, "The Princeton GEO Study: Methodology, Results and Critique", 2025, [vía snippet]): el 30–40% es mejora *relativa* en condiciones favorables (motor de laboratorio, 5 fuentes en contexto), y los métodos permiten fabricar estadísticas/citas, lo que un motor real con verificación penaliza. Trasladarlo 1:1 a Google AI Mode o ChatGPT search es especulativo.

### 1.3 Réplicas y contradicciones 2025–2026
- **[PAPER][TEST] C-SEO Bench (Puerto, Gubri, Green, Oh, Yun; NeurIPS D&B 2025; arXiv 2506.11097; abierto en GitHub 28-sep-2025)**: benchmark en QA (noticias, debates, web) y recomendación de productos (retail, videojuegos, libros) sobre Perplexity, ChatGPT Search y Amazon Rufus. Conclusión textual: **"most current C-SEO methods are largely ineffective, contrary to reported results in the literature"**; "traditional SEO strategies, those aimed at improving the ranking of the source in the LLM context, are significantly more effective"; y "as we increase the number of C-SEO adopters, the overall gains decrease" (juego de suma cero). → **Contradice directamente al paper GEO.**
- **[PAPER] AutoGEO (Wu, Zhong, Kim, Xiong; ICLR 2026; arXiv 2510.11438; abierto)**: extrae automáticamente "reglas de preferencia" de Gemini, GPT y Claude y reescribe documentos; reporta (según geo-optimizer-skill) "+50.99% over baseline" en GEO Score. Las reglas concretas no están en el README; hay que leer el paper. Confirma que las preferencias **difieren por motor**.
- **[PAPER][vía snippet]** "What Gets Cited: Competitive GEO in AI Answer Engines" (SIGIR, jul-2026, arXiv 2605.25517); "CITECHOICE: A Causal Audit of How Document Presentation Redistributes Citation Credit" (sep-2026, arXiv 2609.15164); "Diagnosing and Repairing Citation Failures in GEO" (mar-2026, arXiv 2603.09296); "Don't Measure Once: Measuring Visibility in AI Search" (abr-2026, arXiv 2604.07585); "Optimizing Visibility in Generative Engines: A Critical Survey of GEO (2023-2026)" (jul-2026, arXiv 2607.14035); "When Optimization Becomes Manipulation: Defending Generative Search against Malicious GEO" (sep-2026, arXiv 2609.02964). No pude abrir arxiv.org. Tendencia común de los títulos: la visibilidad es **volátil (hay que medir repetidas veces)**, la **presentación del documento redistribuye el crédito de cita**, y ya se estudian **defensas contra GEO manipulativo** (estadísticas/citas inventadas).

**Recomendación para Benja:** quedarse con lo que sobrevive a C-SEO Bench: (a) rankear bien en el índice que alimenta al motor (Google para AIO/AI Mode/Gemini; Bing para ChatGPT/Copilot), y (b) datos verificables, citas reales y pasajes claros. Nada de estadísticas "hipotéticas" ni citas inventadas: el paper las permite, los motores reales y los papers 2026 las tratan como manipulación.

---

## 2. Cómo funciona hoy cada motor (síntesis de las búsquedas)

- **[OFICIAL][vía snippet] Google AI Overviews**: disponibles en 200+ países y 40+ idiomas desde mayo-2025 (blog.google, "AI Overviews are now available in over 200 countries and territories, and more than 40 languages", mayo-2025). Se alimentan del índice normal de Google (Googlebot). Gary Illyes (Search Central Live, jul-2025): "normal SEO works for ranking in AI Overviews" (searchengineland.com/…-459422, jul-2025).
- **[OFICIAL][vía snippet] Google AI Mode**: lanzado mar-2025 (Labs), todos los usuarios de EE. UU. mayo-2025, 180 países en inglés ago-2025 (searchengineland.com/…-461040), **7-oct-2025: +35 idiomas (incluido español) y +40 países → 200+ territorios** (blog.google/products-and-platforms/products/search/ai-mode-expands-languages-locations/). Google I/O mayo-2026: **1.000 M de usuarios mensuales**, consultas duplicándose cada trimestre [vía snippet]. Es una **pestaña**, no el default (no encontré evidencia de que se haya vuelto default en 2026; marcar como no verificado).
- **[OFICIAL][vía snippet] ChatGPT search**: dos índices: **Bing** + crawler propio **OAI-SearchBot**; reescribe la pregunta en varias búsquedas ("query fan-out"), lee páginas, verifica y cita unas pocas (yoast.com/chatgpt-search; geotoolbox.ai; detekia). "If a page is not in Bing's index, ChatGPT cannot cite it; if it blocks OAI-SearchBot it won't show even if ranks well in Bing" [OPINIÓN de terceros basada en docs de OpenAI, verificar].
- **[TEST][vía snippet] Volatilidad de ChatGPT**: Reddit pasó de ~60% de respuestas citadas (ago-2025) a ~10% (sep-2025), solo en ChatGPT; Perplexity y AI Mode no cambiaron (Profound/Semrush 2025). Reddit traducido automáticamente: 52–73% de las citas de Reddit en AIO en mercados no ingleses (mar–jun 2026) eran páginas traducidas por máquina; ChatGPT cortó Reddit traducido en mayo-2026 (6,14% → 0,66%) (peec.ai statistics 2026). **Relevante para español:** Google AIO está citando Reddit traducido en español.
- **[TEST][vía snippet] Cuota de tráfico referido de IA** (Statcounter, abr-2026): ChatGPT 76,85%, Gemini 9,0%, Perplexity 7,73%, Copilot 3,76%, Claude 2,66%.
- **[CONOCIMIENTO PREVIO – verificar]** Copilot (Microsoft) usa el índice de Bing y sus datos de Bing Maps/Bing Places para lo local; Gemini app usa Google Search grounding (mismo índice que AIO) y Google Maps para lo local; Perplexity usa su propio índice (PerplexityBot) + Yelp/Tripadvisor/Maps para lo local. Estos tres puntos los busqué pero el presupuesto no alcanzó para confirmar con doc oficial 2026.

---

## 3. Qué tipo de contenido citan los LLMs (evidencia con datos)

### 3.1 Overlap de citas con el top-10 orgánico (por qué "primero rankear")
| Motor | Overlap de URLs citadas vs. top-10 Google | Fuente |
|---|---|---|
| Google AI Overviews | ~38% de citas vienen del top-10 en 2026 (bajó de ~76% a mediados de 2025); posición 1 ⇒ 58% de probabilidad de ser citado, posición 10 ⇒ 14% | [TEST][vía snippet] Frase/Peec 2026, estudio 2026 sin nombre en snippet |
| Perplexity | ~28,6% | [TEST][vía snippet] Ahrefs, 15.000 consultas, 2025-26 |
| ChatGPT | 6–8%; **28,3% de las páginas más citadas por ChatGPT tienen cero visibilidad orgánica en Google**; <10% de fuentes citadas por ChatGPT/Gemini/Copilot están en top-10 | [TEST][vía snippet] Ahrefs 2025-26 |
| Overlap entre motores | solo ~11% de dominios citados por ChatGPT y Perplexity a la vez; AIO y AI Mode citan la misma URL solo 13,7% de las veces | [TEST][vía snippet] Peec (30 M citas, mar-2026), Semrush (230.000 prompts, ago–oct 2025), 5WPR "State of AI citations 2026" |

Lectura: **para AIO/AI Mode, rankear en Google sigue siendo el predictor principal** (Illyes lo dice [OFICIAL] y los datos lo confirman aunque el peso baja). **Para ChatGPT, rankear en Google no alcanza: hay que estar en Bing y ser "citable"**.

### 3.2 Características de las páginas citadas
- **[PAPER]** Del paper GEO (abierto): citas a fuentes, citas textuales y estadísticas son lo que más sube el "Position-Adjusted Word Count"; keyword stuffing baja. C-SEO Bench matiza: el efecto es pequeño frente a rankear.
- **[TEST][vía snippet][CONOCIMIENTO PREVIO – verificar]** Estudios 2025-26 (Kevin Indig/Growth Memo, Siege Media "AI search citation study", SE Ranking, BrightEdge, Profound) coinciden en: (1) **respuesta directa en los primeros 1–2 párrafos** ("answer-first"), (2) **pasajes autocontenidos de 100–300 palabras** que se entienden sin el resto de la página ("chunkability"), (3) encabezados H2/H3 formulados como la pregunta del usuario, (4) **listas y tablas** con datos concretos (precios, tiempos, pasos), (5) **frescura** (fecha visible y actualización real; AIO/ChatGPT favorecen contenido reciente), (6) definiciones claras de términos, (7) autor/entidad identificable. No pude abrir estos estudios; tratar los % como no verificados.
- **[OFICIAL][CONOCIMIENTO PREVIO – verificar]** Google (documentación "AI features and your website", 2025): no hay marcado ni fichero especial para AIO/AI Mode; los requisitos son estar indexado y ser elegible para snippet; `nosnippet`/`max-snippet`/`data-nosnippet` controlan qué se puede usar; los datos estructurados ayudan a que Google entienda la página pero **no son requisito para AIO**.
- **[TEST][vía snippet]** Peec.ai (2026): Wikipedia, Reddit y YouTube dominan citas en AIO; Pew (jul-2025): Wikipedia, YouTube y Reddit ~15% cada uno de los enlaces en AI summaries [CONOCIMIENTO PREVIO – verificar cifra].

### 3.3 Diferencias entre motores (qué formatear para cada uno)
- **AIO/AI Mode**: pasajes de tu página indexada + entidades del Knowledge Graph + GBP/Maps para negocios. Premia coincidencia semántica con las sub-consultas del fan-out. Idioma: usa contenido en español si la consulta es en español; pero también traduce (ver Reddit traducido).
- **ChatGPT**: índice Bing + verificación en vivo (ChatGPT-User). Cita menos fuentes (2–4 típico), premia dominios "de confianza" del tema y listados/rankings de terceros. Muy volátil.
- **Perplexity**: más citas por respuesta (5–10), overlap mayor con top-10; favorece páginas frescas y directorios/reseñas.
- **Copilot**: Bing puro; lo que rankee en Bing (con Bing Places para local).

---

## 4. Listados de terceros, reseñas, Reddit, foros, directorios, YouTube

- **[TEST][vía snippet]** "AI-generated local results surface only 32% as many unique businesses as traditional local map packs" (estudio 2026 citado por Verlua/ALM; origen probable Whitespark/BrightLocal). AI Mode "may mention one or two by name — or none at all". Con pocas plazas, **las fuentes agregadoras (listas "mejores X en Montevideo", reseñas) pesan más que la web propia**.
- **[TEST][vía snippet]** Whitespark (2026, 540 consultas, 6 verticales): AIO en 68% de consultas locales; 92% en informacionales, 97% en híbridas ("¿quién hace esto cerca?"), menos en transaccionales puras. Fuentes citadas en respuestas locales: GBP/Maps, reseñas, la web del negocio y **directorios/listicles** (SEJ 580757, 2026).
- **[TEST][vía snippet]** Semrush/Profound 2025-26: dominios más citados en ChatGPT para consultas "best X": Reddit (volátil), Wikipedia, Yelp/Tripadvisor (local), YouTube; en AIO: Reddit, YouTube, Quora + sitios de reseñas. En español no hay equivalentes fuertes de Yelp; en UY/AR pesan: Google Maps/GBP, Facebook, MercadoLibre (para casas contenedores), foros/Reddit r/uruguay r/argentina, Páginas Amarillas, Cylex, directorios de cámaras y grupos de Facebook [OPINIÓN].
- **¿Estar en listados o crear uno propio?** Ambas, en este orden:
  1. **[GEO][TRÁMITE]** Estar en los listados que la IA ya cita para tu vertical/ciudad (preguntar a ChatGPT/AI Mode/Perplexity "mejores cerrajeros en Montevideo" 3 veces cada uno y anotar las fuentes; pedir inclusión o crear ficha).
  2. **[GEO][RANKING]** Crear en el sitio una página comparativa honesta ("Cerrajería 24 h en Montevideo: precios 2026, qué incluye, tiempos") con tabla de precios/rangos, criterios y fecha — esto es "listicle" citable sin fabricar un ranking falso de competidores. Un "top 10" con competidores inventados o sesgado puede ser penalizado y es éticamente dudoso.
  3. **[GEO]** Reseñas en GBP con texto que mencione el servicio y el barrio (la IA extrae frases de reseñas); responder reseñas.
  4. **[GEO]** YouTube: un video corto por servicio (aparece en AIO/AI Mode, YouTube es top-3 fuente citada).
  5. **[GEO]** Reddit/foros: participar honestamente en r/uruguay, r/argentina, grupos de Facebook; no spam. Recordar que ChatGPT bajó Reddit al ~10% en sep-2025: no apostar todo ahí.

---

## 5. Bing Places, Apple Business Connect, Bing Webmaster Tools, IndexNow, crawlers y JavaScript

### 5.1 ¿Importan Bing y Apple para ChatGPT/Copilot?
- **[OFICIAL][vía snippet]** OpenAI docs (developers.openai.com/api/docs/bots, no abierto): OAI-SearchBot "is used to link to and surface websites in search results"; ChatGPT search combina índice propio con datos de Bing (partnership Microsoft; Yoast 2025). → **Bing Webmaster Tools + sitemap + IndexNow** es el "trámite" barato para asegurar estar en el índice que alimenta a ChatGPT y Copilot. [TRÁMITE]
- **[CONOCIMIENTO PREVIO – verificar 2026]** Bing Places alimenta Bing Maps → Copilot para consultas locales; no hay evidencia oficial de que ChatGPT use Bing Places para sus "mapas" de negocios (ChatGPT search mostró mapas/fichas locales desde 2025; la procedencia de datos no está documentada públicamente). Apple Business Connect alimenta Apple Maps/Siri; Apple Intelligence delega a ChatGPT algunas consultas. Ambos son trámites gratis de 20 minutos: hacerlos, sin esperar resultados medibles. [TRÁMITE]
- **[OFICIAL][vía snippet]** ppc.land (2025): OpenAI revisó su documentación: **robots.txt puede no aplicarse a ChatGPT-User** porque el fetch lo inicia un usuario (como los fetchers de Google). OAI-SearchBot y GPTBot sí respetan robots.txt.

### 5.2 Tabla de crawlers de IA (user-agent / qué alimenta / bloquear o permitir)
Fuente principal abierta: `ai-robots-txt/ai.robots.txt` (table-of-bot-metrics.md + robots.json, sep-2026) + documentación oficial vía snippet.

| User-agent (token robots.txt) | Operador | Qué alimenta | Respeta robots.txt | Para Benja |
|---|---|---|---|---|
| `Googlebot` | Google | Índice de Search → **AI Overviews, AI Mode, Gemini grounding** | Sí | **PERMITIR** (bloquearlo te saca de todo) |
| `Google-Extended` | Google | Solo entrenamiento de Gemini/Vertex; **no afecta Search, AIO ni AI Mode** (doc "common crawlers" [OFICIAL vía snippet]) | Sí (token, no bot) | Indiferente; permitir |
| `GoogleOther`, `Google-CloudVertexBot`, `Gemini-Deep-Research`, `GoogleAgent-Mariner`, `Google-NotebookLM` | Google | I+D, Vertex, Deep Research, agentes | Sí | Permitir |
| `OAI-SearchBot` | OpenAI | **Índice de ChatGPT search (citas)** | Sí | **PERMITIR** |
| `ChatGPT-User` | OpenAI | Fetch en vivo cuando un usuario pregunta (verificación/cita) | Parcial (puede ignorar robots.txt, [OFICIAL vía snippet 2025]) | **PERMITIR** |
| `GPTBot` | OpenAI | Entrenamiento de modelos (no búsqueda) | Sí | Permitir (para que el modelo "conozca" la marca) o bloquear si hay política; no afecta citas en ChatGPT search |
| `ChatGPT Agent`, `Operator` | OpenAI | Agentes que navegan | Sí | Permitir |
| `PerplexityBot` | Perplexity | Índice de Perplexity | Sí | **PERMITIR** |
| `Perplexity-User` | Perplexity | Fetch por pedido del usuario | **No** (ai.robots.txt) | No se puede bloquear vía robots; permitir |
| `ClaudeBot` | Anthropic | Entrenamiento | Sí | Permitir/bloquear según política |
| `Claude-SearchBot` | Anthropic | Búsqueda de Claude | Sí | Permitir |
| `Claude-User` | Anthropic | Fetch por usuario | Sí | Permitir |
| `Bingbot` | Microsoft | **Índice Bing → Copilot y ChatGPT search** | Sí | **PERMITIR** |
| `Applebot` / `Applebot-Extended` | Apple | Siri/Spotlight / entrenamiento | Sí | Permitir |
| `Meta-ExternalAgent` / `meta-externalfetcher` | Meta | Entrenamiento / Meta AI fetch | Sí | Permitir (Meta AI en WhatsApp puede citar) |
| `Amazonbot` | Amazon | Alexa | Sí | Permitir |
| `DuckAssistBot`, `YouBot`, `MistralAI-User`, `DeepSeekBot`, `Grok`… | varios | Respuestas IA | Sí (mayoría) | Permitir |
| `Bytespider` | ByteDance | Entrenamiento | **No** | Bloquear vía WAF si consume recursos |
| `CCBot` | Common Crawl | Dataset abierto usado para entrenar muchos LLMs | Sí | Permitir (es la forma de que modelos menores conozcan el negocio) |

**Regla práctica:** para un sitio de servicios locales que quiere leads, **no bloquear ningún crawler de búsqueda/fetch de IA**. El único debate es GPTBot/ClaudeBot (entrenamiento): para Benja, permitir; el contenido es comercial y quiere ser conocido.

### 5.3 JavaScript: los crawlers de IA no lo ejecutan
- **[TEST][vía snippet]** Vercel + MERJ, "The rise of the AI crawler" (dic-2024; sigue siendo la referencia citada en 2026): 500 M+ fetches de GPTBot, **cero evidencia de ejecución de JS**; GPTBot descarga JS 11,5% de las veces pero no lo ejecuta; ClaudeBot descarga JS 23,84% y no lo ejecuta; igual PerplexityBot, Bytespider, Meta. **Excepción: Gemini/Google usa el WRS de Googlebot y sí renderiza**. [posiblemente desactualizado en cifras; conclusión confirmada por artículos 2026: searchoptimo.com, seobro.com, averi.ai]
- **[TEST][vía snippet]** MarketerFirst (2026) probó 4 páginas de producto retail: el precio de Target no era visible para crawlers de IA por venir vía JS.
- Implicancia: **precio, teléfono, WhatsApp, horarios, zonas de cobertura y FAQs deben estar en el HTML inicial** (SSR/estático), no inyectados por JS. Un botón WhatsApp generado por JS no es problema para el usuario, pero el **número y el texto** deben estar en el HTML para que ChatGPT/Perplexity los lean.

---

## 6. Medir tráfico de IA en GA4 y Search Console

### 6.1 Referrers conocidos (fuentes abiertas: Snowplow referers.yml, MalteBerlin/LLM-Referrer, Matomo SearchEngines.yml)
- ChatGPT: `chatgpt.com`, `chat.openai.com` (utm_source también `openai.com`).
- Perplexity: `perplexity.ai`, `www.perplexity.ai`.
- Copilot: `copilot.microsoft.com`, `copilot.cloud.microsoft`, `edgeservices.bing.com`.
- Gemini: `gemini.google.com`, `bard.google.com`.
- Claude: `claude.ai`. Mistral: `chat.mistral.ai`. Meta AI: `meta.ai`. Grok: `grok.com`. DeepSeek: `chat.deepseek.com`. You.com: `you.com`. DuckDuckGo AI: `duck.ai`. Poe: `poe.com`. Otros de la lista LLM-Referrer (100+ hosts, ago-2026): `kimi.com`, `felo.ai`, `genspark.ai`, `iask.ai`, `phind.com`, `t3.chat`, `lumo.proton.me`, `qwen.ai`, `hunyuan.tencent.com`…
- **utm_source=chatgpt.com**: ChatGPT agrega `?utm_source=chatgpt.com` a los links que cita (desde fines de 2024, [CONOCIMIENTO PREVIO]); en GA4 eso llega como `source=chatgpt.com`, `medium=(not set)` → canal "Unassigned" si no hay regla. Por eso la regla debe mirar **Source** (no medium ni referrer).

### 6.2 Regex exacto para GA4 (RE2; escapar los puntos)
Canal personalizado "AI Assistants" — condición: **Fuente de la sesión / Fuente** → *coincide con la expresión regular*:

```
(^|\.)(chatgpt\.com|chat\.openai\.com|openai\.com|perplexity\.ai|copilot\.microsoft\.com|copilot\.cloud\.microsoft|edgeservices\.bing\.com|gemini\.google\.com|bard\.google\.com|claude\.ai|chat\.mistral\.ai|meta\.ai|grok\.com|chat\.deepseek\.com|you\.com|duck\.ai|poe\.com|kimi\.com|felo\.ai|genspark\.ai|iask\.ai|phind\.com)$
```

Versión corta (la que circula en Terminus/Swydo 2026, [vía snippet]): `chatgpt\.com|chat\.openai\.com|perplexity\.ai|claude\.ai|copilot\.microsoft\.com|gemini\.google\.com`.

Pasos: Admin → Configuración de datos → Canales → Grupos de canales → crear grupo (o editar el predeterminado copiándolo) → nuevo canal "AI Assistants" → condición Fuente coincide con regex → **subirlo por encima de "Referral" y de "Organic Social"** (GA4 evalúa de arriba abajo; si Referral está antes, se lo queda) [vía snippet Terminus 2026]. Crear además una **exploración/segmento** con la misma regex sobre `Fuente de la sesión` y cruzarlo con el evento `whatsapp_click` (o el nombre que use Benja) para ver leads por asistente.

- **[OFICIAL][vía snippet]** GA4 agregó un canal nativo **"AI Assistant"** al Default Channel Group el **13-may-2026**; la lista de Google **no incluye Perplexity** (Terminus/Design Copy 2026). → Mantener el canal personalizado.
- Limitaciones: los clics desde **AI Overviews y AI Mode llegan como `google / organic`** (no se distinguen en GA4); Copilot dentro de Bing puede caer como bing/organic o social; apps móviles de ChatGPT a veces no envían referrer (aparece como direct). Usar UTM propios en fichas donde se pueda (GBP no permite editar la URL final con UTM sin riesgo? sí permite: `?utm_source=google&utm_medium=organic&utm_campaign=gbp`).

### 6.3 Search Console
- **[OFICIAL][CONOCIMIENTO PREVIO – verificar]** Jun-2025: Google anunció que los datos de AI Mode se incluyen en el informe de Rendimiento dentro del tipo "Web", **sin poder separarlos**.
- **[OFICIAL][vía snippet]** **3-jun-2026**: Google Search Central Blog "Introducing Search Generative AI performance reports in Search Console" (developers.google.com/search/blog/2026/06/gen-ai-performance-reports): informe dedicado con **impresiones** en AI Mode / AI Overviews / Discover con IA, por URL, país y dispositivo, agrupable por día/semana/mes. **No muestra clics, CTR ni consultas.** Rollout completado el **31-ago-2026** para todos los sitios (SEJ 587836). Hay un **control de opt-out** (WebFX 2026). → Es la única forma oficial de saber si las páginas de Benja aparecen en AIO/AI Mode; revisar mensualmente por URL.

---

## 7. Qué es humo (sé crítico)

### 7.1 llms.txt
- **[OFICIAL][vía snippet]** John Mueller (Reddit, jun-2025): "AFAIK none of the AI services have said they're using LLMs.TXT (and you can tell when you look at your server logs that they don't even check for it)". Gary Illyes (Search Central Live, jul-2025): Google no soporta llms.txt ni planea hacerlo; SEJ (2026): "Google Confirms LLMs.txt Has No Current Implementation".
- **[TEST][vía snippet]** Ahrefs, 137.210 dominios: **97% de los llms.txt no recibieron ni una petición en un mes**. Search Engine Land (2025-26) "Does llms.txt matter? We tracked 10 sites": sin efecto medible.
- **[OFICIAL-spec, abierto]** github.com/AnswerDotAI/llms-txt (Jeremy Howard, 2024; v2 2026): la propuesta dice que OpenAI, Anthropic y Gemini **publican** llms.txt para su documentación y que Lighthouse lo audita como "agentic browsing" — eso significa que lo *escriben para sus docs*, **no que sus crawlers lo lean** para buscar. Es útil para agentes de código que leen documentación técnica, no para un sitio de cerrajería.
- Veredicto: **no perjudica, no ayuda; 10 minutos como máximo, prioridad cero.** [TRÁMITE opcional]

### 7.2 "AI schema", "GEO schema", `.well-known/ai.txt`, `/ai/` endpoints
- No existe ningún tipo de schema.org ni marcado reconocido por Google/OpenAI para "IA". Google [OFICIAL, conocimiento previo] afirma que no hay requisitos especiales para AIO. `ai.txt` (Spawning) y `/ai/` endpoints aparecen en herramientas como geo-optimizer-skill (abierto): esa herramienta reparte 18/100 puntos a llms.txt y 6/100 a "AI Discovery" (ai.txt) **sin ninguna evidencia** de que algún motor los consuma; también cita "JSON-LD lifts LLM extraction from 16% to 54%" atribuido a Semrush sin enlace. **Humo con puntaje.**
- El schema **sí** vale por la vía indirecta: `LocalBusiness` + `Service` + `FAQPage` (aunque FAQ rich result ya no se muestra para la mayoría desde 2023) ayudan a Google a entender la entidad, y Google alimenta AIO/AI Mode/Gemini. Mantener schema por [RANKING], no por [GEO].

### 7.3 "GEO tools" y "AI visibility trackers"
- geo-benchmarks (abierto, getauracite): promete el primer benchmark para Q3-2026; **aún no tiene datos**. geo-score (abierto): rúbrica "opinionated but not invented" que reconoce que parte de sus checks son "field observation". Peec, Profound, Semrush AI Toolkit, Ahrefs Brand Radar: miden menciones/citas por prompt; útiles para **medir**, no para "optimizar". Advertencia de "Don't Measure Once" (arXiv 2604.07585, [vía snippet]): las respuestas cambian entre ejecuciones; un tracker con 1 corrida por prompt es ruido. Para Benja alcanza con una planilla: 10 prompts × 3 motores × 3 corridas al mes.
- Claims a desconfiar: "+115% con citas" (es el caso de una fuente en 5.º lugar), "el 60% de las citas de ChatGPT son de Reddit" (fue un pico de ago-2025 que colapsó en septiembre), "AI search converts 4,4× better" (Semrush 2025, B2B, [CONOCIMIENTO PREVIO]; no aplica a leads de cerrajería).

---

## 8. Qué cambia en búsqueda LOCAL con AI Overviews y AI Mode

- **[TEST][vía snippet]** Whitespark 2026 (SEJ 580757): AIO promedio en **68%** de consultas de negocios locales; local pack solo en **39%** (brecha de 29 puntos). Por intención: informacional 92% AIO; híbrida ("¿quién repara X cerca?") 97%; **transaccional simple ("cerrajero 24 h Pocitos") es la que menos AIO dispara y sigue favoreciendo el local pack**. → Las keywords "money" de Benja siguen siendo territorio del pack + orgánico; el AIO ataca las informacionales y las híbridas ("cuánto cuesta una mudanza en Montevideo", "conviene casa contenedor").
- **[TEST][vía snippet]** Unified Platforms / Do It With You (2026): "near me" cada vez más dispara AIO/AI Mode que nombra **1–3 negocios** antes del pack. AI Mode **no muestra el local pack clásico**; puede mostrar tarjetas de lugares tomadas de **Google Business Profile/Maps** y citar reseñas y la web (Whitespark AI Mode guide; theanswerengine.ai). "AI-generated local results surface only 32% as many unique businesses as traditional local packs".
- **[OFICIAL][CONOCIMIENTO PREVIO – verificar]** Google documenta que AI Mode usa "place cards" con datos de Maps (reseñas, horario, fotos), y que AIO para locales se apoya en el Knowledge Graph/GBP. De ahí que **la ficha GBP sea la base de datos primaria de la IA de Google para negocios**: categoría principal correcta, servicios cargados, zonas, horario 24 h real, fotos, reseñas con texto, Q&A y posteos.
- **[TEST][vía snippet]** Uso de IA para búsqueda local por consumidores: de ~6% (2025) a ~45% (2026) (encuesta citada por Elev8/Angarum 2026; metodología no verificada, tratar con cautela).
- **Español / LatAm / UY-AR**:
  - AIO: **[OFICIAL vía snippet]** disponibles en 200+ países y 40+ idiomas desde may-2025 (excepto Cuba, Irán, China continental) → **Uruguay y Argentina incluidos, en español**. [CONOCIMIENTO PREVIO] La expansión a LatAm en español había empezado en oct-2024 (100+ países, incl. AR/UY/MX/CL…); verificar fecha exacta.
  - AI Mode: **[OFICIAL vía snippet]** 7-oct-2025: 35+ idiomas nuevos (español incluido) y 40+ países nuevos; en Américas se nombran EE. UU., Canadá, México, Brasil, **Argentina** y varios de Centroamérica/Caribe. **Uruguay no aparece nombrado en el snippet**, aunque Google habla de "200+ países y territorios"; **verificar abriendo google.com desde UY** (pestaña "Modo IA"). Marcar como *probable* hasta confirmar.
  - No encontré ningún estudio 2025-26 con % de AIO en consultas locales en español o en UY/AR. Los datos de Whitespark son EE. UU./inglés. **Benja puede generar el dato propio**: 50 consultas de sus verticales × 2 países × 3 corridas y anotar si aparece AIO, pack, y qué fuentes cita. Ese dato vale más que cualquier estudio en inglés.
  - Riesgo específico en español: AIO cita Reddit traducido automáticamente (52–73% de las citas de Reddit en mercados no ingleses, mar–jun 2026, [vía snippet Peec]) → hay poco contenido local en español "citable" y la IA rellena con traducciones. **Oportunidad**: contenido en español rioplatense con precios en UYU/ARS y barrios reales tiene poca competencia citable.

---

## 9. Frameworks GEO 2025-2026 con datos (lo que se pudo constatar)

Advertencia: el presupuesto de búsqueda se agotó antes de poder abrir a estos autores; lo siguiente mezcla snippets y conocimiento previo. Marcado como [OPINIÓN] salvo que se indique.

- **Kevin Indig (Growth Memo)** [TEST/OPINIÓN][CONOCIMIENTO PREVIO]: estudios de comportamiento con usuarios en AI Mode/AIO (2025) → menos clics, la gente confía en la respuesta; análisis de citas en AIO que muestra correlación decreciente con posición y peso de "answer-first" y frescura. Marco: "visibilidad = ser citado, no rankear".
- **Aleyda Solís** [OPINIÓN]: framework "LEO/LLM-EO" y su checklist de AI search (learningaisearch/aleydasolis.com, 2025): auditar prompts, entidades, contenido citable, tracking de referrers, GSC AI report. No abierto.
- **Bernard Huang (Clearscope)** [OPINIÓN][CONOCIMIENTO PREVIO]: pionero en explicar el **query fan-out** de AI Mode (Google confirmó la técnica en I/O 2025 [OFICIAL]) y en probar que AI Mode reformula la consulta en N sub-consultas → optimizar para el "cluster" de sub-preguntas, no para una keyword.
- **Mike King (iPullRank)** [OPINIÓN][CONOCIMIENTO PREVIO]: "Relevance Engineering"; AI Mode recupera **pasajes**, no páginas (patentes de Google sobre "passage-level retrieval" y "query fan-out" [FILTRACIÓN/PATENTE]); recomienda pasajes densos, autocontenidos, con la entidad nombrada explícitamente en cada chunk.
- **Andrea Volpini (WordLift)** [OPINIÓN]: entidad + Knowledge Graph + schema consistente (sameAs, GBP ↔ web ↔ Wikipedia/Wikidata cuando aplica) para que la IA resuelva "quién es este negocio".
- **Ross Hudgens / Siege Media "AI search citation study" (2025)** [TEST][CONOCIMIENTO PREVIO – verificar]: listas/estadísticas/comparativas son los formatos más citados; dominios con autoridad y frescura ganan; pocos resultados citados vienen de páginas de servicio "delgadas".
- **Semrush AI visibility (2025-26)** [TEST][vía snippet]: 230.000 prompts, ago–oct 2025, ChatGPT/AI Mode/Perplexity: dominios citados difieren por motor; overlap bajo; Reddit/Wikipedia/YouTube arriba.
- **Ahrefs Brand Radar (2025-26)** [TEST][vía snippet]: 28,3% de las páginas más citadas por ChatGPT sin visibilidad orgánica; 12% overlap global con top-10; -58% CTR en posición 1 con AIO (dic-2025, 300k keywords).
- **Peec AI (2026)** [TEST][vía snippet]: 30 M citas, mar-2026: AIO 38% top-10; AIO vs AI Mode 13,7% misma URL; Reddit traducido.
- Convergencia real de todos los frameworks: (1) rankear/indexar en el índice fuente, (2) pasajes autocontenidos "answer-first" con datos, (3) entidad consistente (GBP + schema + menciones), (4) presencia en fuentes de terceros que la IA ya cita, (5) medir con referrers + GSC AI report.

---

## Checklist GEO propuesta (página + sitio) — etiquetas [GEO] / [RANKING] / [TRÁMITE]

### A. Sitio (una vez por proyecto)
- [ ] [RANKING] Indexado y rankeando en Google para servicio + ciudad (sin esto no hay AIO/AI Mode). Verificar en GSC.
- [ ] [TRÁMITE] Bing Webmaster Tools: verificar sitio, enviar sitemap, activar **IndexNow** (plugin o clave) → índice Bing → ChatGPT search y Copilot.
- [ ] [TRÁMITE] Bing Places (importar desde GBP), Apple Business Connect. 20 minutos, sin expectativa de medir.
- [ ] [GEO] robots.txt: **permitir** Googlebot, Bingbot, OAI-SearchBot, ChatGPT-User, PerplexityBot, Claude-SearchBot, Applebot, Meta-ExternalAgent; no bloquear Google-Extended por error pensando que "protege" (no afecta AIO). Decidir GPTBot/ClaudeBot (recomendado: permitir).
- [ ] [GEO] HTML estático/SSR: NAP, WhatsApp (número visible como texto + link `wa.me`), precios, zonas, horarios y FAQs en el HTML inicial, no vía JS.
- [ ] [RANKING] Schema `LocalBusiness` (subtipo Locksmith, MovingCompany, Electrician, HomeAndConstructionBusiness) + `Service` + `areaServed` + `sameAs` (GBP, Facebook, Instagram, directorios) + `FAQPage` en páginas de servicio. Coherente 100% con la ficha GBP.
- [ ] [GEO] Página "Sobre nosotros / Quiénes somos" con entidad real: nombre, RUT/CUIT si corresponde, años, técnicos, zonas, fotos reales. La IA pregunta "¿quién es esta empresa?".
- [ ] [GEO] GA4: canal personalizado "AI Assistants" con la regex del punto 6.2, por encima de Referral; exploración cruzada con evento WhatsApp. Revisar GSC "Generative AI performance" mensual por URL.
- [ ] [GEO][TRÁMITE opcional] llms.txt: solo si sobra tiempo; no medir nada con esto.
- [ ] [GEO] Presencia en listados de terceros que la IA cita en UY/AR (relevar con 10 prompts × 3 motores × 3 corridas; anotar dominios; gestionar inclusión).
- [ ] [GEO] GBP completa: categoría principal correcta, servicios con descripción, atributos, horario real 24 h, fotos, Q&A propio, 1 post/mes, respuesta a reseñas; pedir reseñas que mencionen servicio + barrio.

### B. Página de servicio + ciudad (cada landing)
- [ ] [GEO] **Answer-first**: primer párrafo (40–70 palabras) responde qué, dónde, cuánto y cómo contactar. Ej.: "Cerrajería 24 h en Montevideo: apertura de puertas desde $U X, llegada en 30–45 min en Pocitos, Cordón, Centro… Pedilo por WhatsApp".
- [ ] [GEO] H2/H3 formulados como preguntas reales de usuario ("¿Cuánto cuesta abrir una puerta en Montevideo en 2026?"), cada sección autocontenida (100–300 palabras), sin depender de "como dijimos arriba".
- [ ] [GEO] **Tabla de precios/rangos** (UYU/ARS, fecha de vigencia) + tabla de tiempos de llegada por zona + lista de qué incluye/no incluye. Datos reales del negocio, no "estadísticas hipotéticas".
- [ ] [GEO] Datos con fuente cuando se citen (normativa, UTE, Intendencia, BPS, etc.) y citas textuales reales (cliente, técnico) con nombre. Nada inventado.
- [ ] [GEO] Fecha de publicación **y** de actualización visibles + `dateModified` en schema; actualizar precios cada 3–6 meses (la inflación en AR obliga; en UY al menos semestral).
- [ ] [GEO] Entidad nombrada en los pasajes clave ("En **Cerrajería X** cubrimos…"), para que el chunk citado lleve la marca.
- [ ] [RANKING] Title/H1 con servicio + ciudad, enlaces internos entre servicio ↔ barrio ↔ FAQ, sin canibalización.
- [ ] [GEO] FAQ de 5–8 preguntas con respuestas de 2–4 líneas (formato ideal para AIO/ChatGPT).
- [ ] [GEO] Un video corto (YouTube) embebido por servicio, con título pregunta.
- [ ] [GEO] No: keyword stuffing, "top 10" con competidores inventados, estadísticas sin fuente, contenido traducido automático.

---

## Implicancias para Benja

1. **El pack local y el orgánico siguen siendo el negocio en las keywords transaccionales** ("cerrajero urgente Montevideo", "mudanzas Pocitos"): AIO aparece menos ahí y AI Mode es una pestaña que la mayoría no usa. Priorizar [RANKING] + GBP como siempre; GEO es capa encima, no reemplazo.
2. **Donde sí muerde la IA es en las consultas informacionales e híbridas** (precios, "conviene", "qué incluye", "casa contenedor vs tradicional"): 92–97% con AIO en inglés/EE. UU. Ahí la CTR orgánica cae ~58–61% [Ahrefs/Seer 2025], pero **ser citado sube CTR +35% orgánico** [Seer]. Estrategia: páginas informacionales en rioplatense con precios reales y fecha, diseñadas para ser el pasaje citado, con CTA WhatsApp en el HTML.
3. **Casas contenedores** es el vertical más "GEO": mucha consulta informacional (precios, permisos, m², plazos), poco contenido citable en español. Una guía con tabla de precios UYU/ARS por m², plazos y normativa municipal, actualizada, tiene chances reales de ser citada por AIO/ChatGPT/Perplexity.
4. **Cerrajería/electricista/mudanzas**: la IA nombra 1–3 negocios sacados de GBP/reseñas y de listados. Inversión: reseñas con texto descriptivo, ficha completa, y estar en los 3–5 listados que los motores ya citan para "mejores X en Montevideo/Buenos Aires" (relevar).
5. **ChatGPT ≠ Google**: rankear en Google no garantiza citas en ChatGPT (6–8% overlap). Trámites de Bing (Webmaster Tools + IndexNow + Bing Places) son gratis y cubren ChatGPT + Copilot.
6. **Medición**: canal "AI Assistants" en GA4 con la regex exacta del punto 6.2, cruzado con el evento WhatsApp; GSC AI report (impresiones por URL, desde ago-2026). Aceptar que clics desde AIO/AI Mode se ven como google/organic. Esperar volúmenes chicos: la IA es ~2–5% del tráfico referido en la mayoría de sitios locales [OPINIÓN], pero con intención alta.
7. **No gastar en**: llms.txt (prioridad cero), "AI schema", herramientas de GEO con puntajes, contenido con estadísticas inventadas o "citas" fabricadas (el paper las usa; los motores 2026 las penalizan).
8. **Uruguay**: confirmar manualmente que la pestaña "Modo IA" aparece en google.com.uy (Argentina confirmado en oct-2025). AIO en español ya activo en ambos países.
9. **Contenido en español real gana por default**: AIO en mercados no ingleses cita Reddit traducido por máquina en 52–73% de sus citas de Reddit; hay hueco para fuentes locales bien escritas.

---

## Contradicciones encontradas

| Tema | Postura A | Postura B | Qué aplicar para Benja |
|---|---|---|---|
| ¿Funcionan las técnicas GEO (citas, estadísticas, quotes)? | Paper GEO (KDD 2024): hasta +40% [PAPER] | C-SEO Bench (NeurIPS 2025): "largely ineffective"; rankear en el contexto del LLM vale más [PAPER] | Aplicar las técnicas solo con datos **reales** y como capa sobre [RANKING]; no esperar +40%. |
| Tono "autoritativo" | GEO paper: mejora subjetiva leve | geo-score/lectura del paper: sin mejora significativa en word-count | Ignorar el tono; poner datos. |
| Google-Extended | Muchos posts: "bloquearlo te saca de AI Overviews" | Google docs [OFICIAL]: solo afecta entrenamiento Gemini/Vertex; AIO usa Googlebot | Doc oficial. No tocar Google-Extended pensando en AIO. |
| ChatGPT-User y robots.txt | Docs 2024: respeta robots.txt | Docs revisadas 2025 [OFICIAL vía snippet]: puede no aplicar (fetch iniciado por usuario) | Asumir que no se puede bloquear; permitir todo. |
| llms.txt | Spec (Answer.AI) + vendors de GEO: "OpenAI y Anthropic lo adoptaron" | Mueller/Illyes 2025 + logs Ahrefs (97% sin requests): nadie lo lee | Google/logs. Prioridad cero. |
| Overlap AIO vs top-10 | 2025: ~76% de las citas del top-10 | 2026: ~38% (Peec) | Ambos son ciertos en el tiempo: el peso del ranking baja pero sigue siendo el mayor predictor. Rankear + citable. |
| Reddit como fuente | Ago-2025: 60% de respuestas ChatGPT citan Reddit | Sep-2025: 10% | No construir estrategia sobre Reddit; participar orgánicamente. |
| ¿AIO reemplaza al pack local? | Whitespark 2026: AIO 68% vs pack 39% | Mismo estudio: transaccionales simples siguen con pack | Segmentar por intención: transaccional → pack/orgánico; informacional/híbrida → GEO. |
| AI Mode en Uruguay | Google: "200+ países" (oct-2025) | Lista de Américas no nombra Uruguay | Verificar manualmente desde UY. |
| Efecto de CTR con AIO | Ahrefs abr-2025: -34,5% | Ahrefs dic-2025: -58% (pos. 1); Seer: -61%; Pew: 8% vs 15% | Tomar -50/60% como orden de magnitud en informacionales. |
| Adopción de IA para local | Encuestas 2026: 6% → 45% en un año | Statcounter: IA = fracción pequeña del tráfico referido | Las encuestas miden "uso alguna vez"; el tráfico real sigue chico. Medir lo propio. |

---

## Fuentes (URL + fecha) — resumen

Abiertas (GitHub): https://github.com/GEO-Optim/GEO (README, src/geo_functions.py, src/run_geo.py, docs/GEO/index.html, GEO-Bench/leaderboard; repo actualizado 30-oct-2025) · https://github.com/parameterlab/c-seo-bench (sep-2025; arXiv 2506.11097) · https://github.com/cxcscmu/AutoGEO (ICLR 2026, aceptado 28-ene-2026; arXiv 2510.11438) · https://github.com/ai-robots-txt/ai.robots.txt (table-of-bot-metrics.md, robots.json, robots.txt; sep-2026) · https://github.com/AnswerDotAI/llms-txt (spec v2, 2026) · https://github.com/MalteBerlin/LLM-Referrer (llm-referrer.txt, 2026) · https://github.com/snowplow-referer-parser/referer-parser (referers.yml, categoría chatbot) · https://github.com/matomo-org/searchengine-and-social-list (SearchEngines.yml) · https://github.com/jianruntech/geo-score · https://github.com/Auriti-Labs/geo-optimizer-skill · https://github.com/getauracite/geo-benchmarks · https://github.com/haofeix/google-aio-characterization (dataset aún no publicado).

Vía snippet (no abiertas; verificar): https://arxiv.org/abs/2311.09735 · https://arxiv.org/pdf/2605.25517 · https://arxiv.org/pdf/2609.15164 · https://arxiv.org/pdf/2603.09296 · https://arxiv.org/pdf/2604.07585 · https://arxiv.org/pdf/2607.14035 · https://arxiv.org/pdf/2609.02964 · https://www.searchenginejournal.com/ai-overviews-now-answer-most-local-searches-how-to-get-your-business-cited/580757/ (Whitespark, 2026) · https://whitespark.ca/guides/whitesparks-guide-to-googles-ai-mode-for-local-businesses/ · https://www.pewresearch.org/short-reads/2025/07/22/google-users-are-less-likely-to-click-on-links-when-an-ai-summary-appears-in-the-results/ (22-jul-2025) · https://www.seerinteractive.com/news/seer-interactive-research-featured-in-inc.-analysis-of-ctr-and-ai-overviews (sep-2025) · https://ahrefs.com/blog/ai-overviews-reduce-clicks-update (dic-2025) · https://searchengineland.com/google-says-normal-seo-works-for-ranking-in-ai-overviews-and-llms-txt-wont-be-used-459422 (jul-2025) · https://www.searchenginejournal.com/google-says-llms-txt-is-purely-speculative-for-now/577576/ · https://searchengineland.com/does-llms-txt-matter-467740 · https://developers.openai.com/api/docs/bots · https://ppc.land/openai-revises-chatgpt-crawler-documentation-with-significant-policy-changes/ · https://yoast.com/chatgpt-search/ · https://vercel.com/blog/the-rise-of-the-ai-crawler (dic-2024) · https://developers.google.com/search/blog/2026/06/gen-ai-performance-reports (3-jun-2026) · https://www.searchenginejournal.com/google-search-console-ai-reports-rolled-out-worldwide/587836/ (ago-2026) · https://blog.google/products-and-platforms/products/search/ai-overview-expansion-may-2025-update/ (may-2025) · https://blog.google/products-and-platforms/products/search/ai-mode-expands-languages-locations/ (7-oct-2025) · https://searchengineland.com/google-launches-ai-mode-in-180-countries-and-territories-461040 (ago-2025) · https://peec.ai/ai-search-geo-statistics (2026) · https://www.tryprofound.com/blog/ai-platform-citation-patterns · https://www.frase.io/blog/which-ai-engines-cite-which-sources (2026) · https://www.5wpr.com/research/state-of-ai-citations-2026/ · https://www.terminusapp.com/blog/ai-traffic-channel-in-ga4/ (2026) · https://www.swydo.com/blog/track-ai-traffic-in-ga4/ · https://blckalpaca.at/en/knowledge-base/seo-geo/geo-generative-engine-optimization/the-princeton-geo-study-methodology-results-and-critique · https://www.menra.ai/guides/ai-overviews-crawler-guide · https://marketerfirst.com/hub/what-ai-crawlers-can-read-on-product-pages/ (2026).

---

## Anexo: protocolo mínimo de relevamiento propio (UY/AR, 2 horas/mes)

1. Armar 10 prompts por vertical y ciudad, mitad transaccionales ("cerrajero 24 h en Pocitos"), mitad informacionales/híbridas ("cuánto cuesta una mudanza de 2 ambientes en Montevideo 2026").
2. Correr cada prompt 3 veces en: Google (anotar si hay AIO y si hay pack), pestaña Modo IA, ChatGPT (con búsqueda), Perplexity, Copilot. Anotar negocios nombrados y dominios citados.
3. Consolidar en planilla: % de prompts con AIO, % con pack, dominios de terceros recurrentes (candidatos a listados), páginas propias citadas.
4. Cruzar con GSC "Generative AI performance" (impresiones por URL) y GA4 canal "AI Assistants" → evento WhatsApp.
5. Repetir mensualmente; la volatilidad entre corridas es normal ("Don't Measure Once", 2026): mirar tendencias, no una foto.
