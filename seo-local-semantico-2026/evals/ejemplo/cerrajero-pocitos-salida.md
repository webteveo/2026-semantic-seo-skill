# Página `cerrajero.uy/pocitos/` — lista para pegar en la plantilla PHP

## 1. Resumen

- **[RANKING]** La zona cumple las dos condiciones para tener URL propia: Pocitos tiene demanda propia ("cerrajero Pocitos" es de los ~20 barrios de Montevideo buscados por nombre) y la fila de datos está completa (tiempo, 3 trabajos, reseña, precios, subzonas). Pasa el test del nombre: Benito Blanco, 26 de Marzo, la rambla, Villa Biarritz y Pocitos Nuevo identifican la zona sin el topónimo.
- **[RANKING]** URL `/pocitos/` (EMD mono-servicio, jerarquía home → `/montevideo/` → `/pocitos/`). Title 50 caracteres con gancho propio (tiempo de llegada), H1 61 caracteres alineado, description 147 con "por WhatsApp" y precio "desde" real.
- **[CONVERSIÓN]** WhatsApp prellenado con servicio + zona en hero y CTA final, botón llamar, `data-servicio`/`data-zona` para `click_wsp`; el sticky lo pone la plantilla global.
- **[TRÁMITE]** JSON-LD B adaptado a EMD (Service + provider `@id` + BreadcrumbList de 3 niveles + WebPage). Sin `aggregateRating`/`review`. FAQ visible, sin FAQPage (no rinde desde may-2026).
- **[GEO]** Primer párrafo answer-first de 70 palabras con marca, base, tiempo, precio y dato exclusivo; tabla de precios en UYU con fecha; fecha de actualización visible. **Riesgo a evitar**: no publicar la página huérfana (enlazarla el mismo día desde home, `/montevideo/` y una vecina) ni afirmar "24 hs" si el operador no atiende de madrugada; ver supuestos en §6.

**Title (50):** `Cerrajero en Pocitos 24 hs – Llegamos en 15-25 min`
**Meta description (147):** `Cerrajero 24 hs en Pocitos, Montevideo. Apertura sin romper desde $U 1.900, precio por WhatsApp antes de salir. Llegamos en 15-25 min desde Cordón.`
**H1 (61):** `Cerrajero en Pocitos: llegamos en 15–25 minutos, las 24 horas`

Alternativa de title si el gancho de tiempo no se quiere en el title (53): `Cerrajero en Pocitos – Apertura desde $U 1.900, 24 hs`.

## 2. Bloque `<head>`

```html
<title>Cerrajero en Pocitos 24 hs – Llegamos en 15-25 min</title>
<meta name="description" content="Cerrajero 24 hs en Pocitos, Montevideo. Apertura sin romper desde $U 1.900, precio por WhatsApp antes de salir. Llegamos en 15-25 min desde Cordón.">
<link rel="canonical" href="https://cerrajero.uy/pocitos/">
<meta property="og:title" content="Cerrajero en Pocitos 24 hs – Llegamos en 15-25 min">
<meta property="og:description" content="Apertura sin romper desde $U 1.900. Salimos desde Cordón y llegamos a Pocitos en 15-25 minutos. Precio por WhatsApp antes de salir.">
<meta property="og:url" content="https://cerrajero.uy/pocitos/">
<meta property="og:type" content="website">
<meta property="og:locale" content="es_UY">
<!-- JSON-LD: pegar el bloque de la sección 4 acá -->
```

## 3. Bloque HTML de `<main>`

Convenciones: `{variables}` = dato que el operador no dio (lista en §6). Español rioplatense. WhatsApp en E.164 sin "+" para `wa.me`, visible como 099 123 456.

```html
<nav class="breadcrumb" aria-label="Ubicación">
  <a href="https://cerrajero.uy/">Inicio</a> › <a href="https://cerrajero.uy/montevideo/">Montevideo</a> › <span>Pocitos</span>
</nav>

<!-- 1. HERO -->
<section class="hero">
  <h1>Cerrajero en Pocitos: llegamos en 15–25 minutos, las 24 horas</h1>
  <p class="hero-sub">Salimos desde Cordón (Constituyente y Canelones). Apertura desde $U 1.900 · Cambio de cerradura desde $U 2.800 · {Garantía / matrícula}.</p>
  <p class="hero-cta">
    <a class="cta-wsp" data-servicio="cerrajero" data-zona="pocitos" rel="noopener" target="_blank"
       href="https://wa.me/59899123456?text=Hola,%20necesito%20un%20cerrajero%20en%20Pocitos">Escribir por WhatsApp</a>
    <a class="cta-call" href="tel:+59899123456">Llamar 099 123 456</a>
  </p>
  <p class="hero-proof">★ {rating} · {n_reseñas} reseñas en Google · {credencial: matrícula / años en el oficio}</p>
  <img src="https://cerrajero.uy/img/cerrajero-pocitos-real.webp" alt="Cerrajero de {Marca} abriendo una puerta blindada en un edificio de Pocitos, Montevideo" width="1200" height="800" fetchpriority="high" decoding="async">
</section>

<!-- 2. PRIMER PÁRRAFO answer-first (70 palabras) -->
<p class="lead">{Marca} es cerrajero en Pocitos las 24 horas: apertura sin romper la cerradura, cambio de cerraduras y cilindros europeos, y llaves rotas. Salimos desde nuestra base en Cordón (Constituyente y Canelones) y llegamos en 15–25 minutos de día, unos 30 de noche. Trabajamos seguido en edificios de la rambla y puertas blindadas de Benito Blanco. Apertura desde $U 1.900 (septiembre 2026); te confirmamos el precio por WhatsApp antes de salir.</p>

<!-- 3. BARRA DE CONFIANZA -->
<ul class="trust-bar">
  <li>{años} años en Montevideo</li>
  <li>{n_trabajos}+ trabajos</li>
  <li>{garantía}</li>
  <li>{matrícula / RUT / seguro}</li>
  <li>Precio confirmado por WhatsApp antes de salir</li>
</ul>

<!-- 4. SERVICIOS EN LA ZONA -->
<section>
  <h2>Servicios de cerrajería en Pocitos</h2>
  <div class="cards">
    <article>
      <h3><a href="https://cerrajero.uy/apertura-de-puertas/">Apertura de puertas en Pocitos</a></h3>
      <p>Si te quedaste afuera, abrimos sin romper la cerradura, incluidas puertas blindadas. Desde $U 1.900; de noche, +30 %.</p>
    </article>
    <article>
      <h3><a href="https://cerrajero.uy/cambio-de-cerradura/">Cambio de cerradura y cilindro</a></h3>
      <p>Cambiamos cerraduras completas y cilindros europeos, los más comunes en los edificios de la rambla. Mano de obra desde $U 2.800 más la cerradura que elijas.</p>
    </article>
    <article>
      <h3>Llave rota adentro de la cerradura</h3>
      <p>Sacamos el pedazo de llave sin dañar el cilindro y, si hace falta, hacemos el cambio en la misma visita. Precio {precio_llave_rota}, te lo pasamos por WhatsApp.</p>
    </article>
  </div>
</section>

<!-- 5. TRABAJOS RECIENTES -->
<section>
  <h2>Trabajos recientes en Pocitos</h2>
  <table class="jobs">
    <thead><tr><th>Fecha</th><th>Trabajo</th><th>Referencia</th><th>Tiempo de llegada</th></tr></thead>
    <tbody>
      <tr><td>Marzo 2026</td><td>Apertura de puerta blindada sin daños</td><td>Benito Blanco</td><td>25 min</td></tr>
      <tr><td>Abril 2026</td><td>Cambio de cilindro europeo en apartamento</td><td>Edificio de la rambla</td><td>{tiempo_trabajo_2} min</td></tr>
      <tr><td>Mayo 2026</td><td>Extracción de llave rota adentro de la cerradura</td><td>26 de Marzo</td><td>{tiempo_trabajo_3} min</td></tr>
    </tbody>
  </table>
  <figure>
    <img src="https://cerrajero.uy/img/cerrajero-pocitos-trabajo.webp" alt="{Qué se ve en la foto real, ej. cilindro europeo nuevo instalado en puerta de apartamento en Pocitos}" width="900" height="600" loading="lazy" decoding="async">
    <figcaption>{Descripción honesta del trabajo fotografiado, mes 2026}.</figcaption>
  </figure>
</section>

<!-- 6. RESEÑAS DE LA ZONA -->
<section>
  <h2>Opiniones de vecinos de Pocitos</h2>
  <blockquote>
    <p>“Vino en 20 minutos a Pocitos y abrió sin romper nada, precio claro”</p>
    <footer>Lucía, Pocitos · Mayo 2026 · <a href="{url_ficha_google}" rel="noopener" target="_blank">Ver en Google</a></footer>
  </blockquote>
</section>

<!-- 7. CÓMO LLEGAMOS + PROCESO -->
<section>
  <h2>Cómo llegamos a Pocitos</h2>
  <p>Salimos desde Constituyente y Canelones, en Cordón, {ruta habitual, ej. por Bulevar España o Av. Brasil}. De día tardamos 15–25 minutos según el tránsito; de noche, unos 30. Desde la misma salida cubrimos Pocitos Nuevo y Villa Biarritz con el mismo tiempo.</p>
  <ol class="steps">
    <li>Nos escribís por WhatsApp con la dirección y, si podés, una foto de la cerradura o de la puerta.</li>
    <li>Te pasamos el precio antes de salir.</li>
    <li>Llegamos en 15–25 minutos y abrimos o cambiamos la cerradura sin romper la puerta.</li>
    <li>Pagás al terminar: {medios de pago}. {Garantía sobre el trabajo}.</li>
  </ol>
</section>

<!-- 8. PRECIOS CON FECHA -->
<section>
  <h2>Precios de cerrajero en Pocitos (septiembre 2026)</h2>
  <table class="prices">
    <thead><tr><th>Trabajo</th><th>Desde</th><th>Incluye</th></tr></thead>
    <tbody>
      <tr><td>Apertura de puerta</td><td>$U 1.900</td><td>Traslado a Pocitos y apertura sin romper la cerradura</td></tr>
      <tr><td>Cambio de cerradura o cilindro</td><td>$U 2.800 + cerradura</td><td>Traslado, mano de obra y colocación; la cerradura se cotiza aparte según modelo</td></tr>
      <tr><td>Llave rota adentro</td><td>{precio_llave_rota}</td><td>Extracción de la llave; cambio de cilindro aparte si quedó dañado</td></tr>
      <tr><td>Recargo nocturno</td><td>+30 %</td><td>{franja nocturna, ej. de 22 a 7 h}</td></tr>
    </tbody>
  </table>
  <p class="note">Precios orientativos vigentes a septiembre 2026. Te confirmamos el precio por WhatsApp antes de salir.</p>
</section>

<!-- 9. ZONA Y COBERTURA -->
<section>
  <h2>Dónde trabajamos en Pocitos</h2>
  <p>La mayoría de los llamados son de apartamentos en edificios de la rambla y de las calles internas, con cilindro europeo o puerta blindada; ahí el trabajo es abrir sin dañar el cilindro para que sigas usando tu llave. Lo más frecuente es quedarse afuera con la llave adentro o que la llave se rompa en la cerradura. Referencias: la rambla, Benito Blanco y 26 de Marzo. Cubrimos también Pocitos Nuevo y Villa Biarritz.</p>
</section>

<!-- 10. FAQ LOCAL -->
<section class="faq">
  <h2>Preguntas frecuentes de Pocitos</h2>
  <h3>¿Cuánto tarda en llegar un cerrajero a Pocitos?</h3>
  <p>Entre 15 y 25 minutos de día y unos 30 de noche, porque salimos desde Cordón (Constituyente y Canelones). Al escribirnos por WhatsApp te confirmamos el tiempo real según el tránsito.</p>
  <h3>¿Cuánto cuesta abrir una puerta en Pocitos?</h3>
  <p>Desde $U 1.900 (vigente a septiembre 2026), con traslado incluido. De noche el recargo es del 30 %. Las puertas blindadas también las abrimos sin romper; te pasamos el precio cerrado antes de salir.</p>
  <h3>¿Llegan a Pocitos Nuevo y Villa Biarritz?</h3>
  <p>Sí, salimos desde la misma base y el tiempo es el mismo: 15–25 minutos de día y unos 30 de noche.</p>
  <h3>¿Cuánto cobra un cerrajero en Pocitos de noche?</h3>
  <p>Lo mismo que de día más un 30 %: la apertura queda desde $U 2.470 y el cambio de cerradura desde $U 3.640 más la cerradura. {Confirmar franja horaria del recargo}.</p>
  <h3>Se me rompió la llave adentro de la cerradura, ¿hay que cambiarla?</h3>
  <p>No siempre. Primero sacamos el pedazo de llave; si el cilindro no se dañó, sigue funcionando. Si quedó trabado, lo cambiamos en la misma visita (desde $U 2.800 más el cilindro).</p>
</section>

<!-- 11. CTA FINAL (el botón sticky móvil lo pone la plantilla global) -->
<section class="cta-final">
  <h2>Cerrajero en Pocitos ahora</h2>
  <p>Escribinos y te confirmamos precio y tiempo de llegada en minutos.</p>
  <a class="cta-wsp" data-servicio="cerrajero" data-zona="pocitos" rel="noopener" target="_blank" href="https://wa.me/59899123456?text=Hola,%20necesito%20un%20cerrajero%20en%20Pocitos">WhatsApp 099 123 456</a>
</section>

<!-- 12. ZONAS CERCANAS + MADRE -->
<section class="nearby">
  <h2>También llegamos cerca de Pocitos</h2>
  <p>Si estás en <a href="https://cerrajero.uy/punta-carretas/">Punta Carretas</a>, necesitás <a href="https://cerrajero.uy/buceo/">urgencias en Buceo</a> o vivís en <a href="https://cerrajero.uy/parque-batlle/">Parque Batlle</a>, el tiempo de llegada es similar; en <a href="https://cerrajero.uy/cordon/">Cordón</a>, donde está nuestra base, es menor. Para el resto de la ciudad, ver <a href="https://cerrajero.uy/montevideo/">cerrajero en Montevideo</a>.</p>
  <p class="updated">Última actualización: {fecha_visible, ej. 24 de septiembre de 2026}.</p>
</section>
```

## 4. JSON-LD (pegar en el `<head>`)

Plantilla B de `entidades-y-schema.md` adaptada a EMD mono-servicio: sin nivel `{servicio_slug}` y con `/montevideo/` como nivel 2 del breadcrumb. `provider` referencia el `@id` del `Locksmith` que ya debe existir en la home (`https://cerrajero.uy/#negocio`).

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@graph": [
    {
      "@type": "Service",
      "@id": "https://cerrajero.uy/pocitos/#servicio",
      "name": "Cerrajero en Pocitos",
      "serviceType": "Cerrajería",
      "description": "Cerrajero en Pocitos, Montevideo. Llegamos en 15–25 minutos desde Cordón. Apertura de puertas, cambio de cerradura y llaves rotas. Presupuesto por WhatsApp.",
      "provider": { "@id": "https://cerrajero.uy/#negocio" },
      "areaServed": {
        "@type": "City",
        "name": "Pocitos",
        "containedInPlace": { "@type": "AdministrativeArea", "name": "Montevideo" }
      },
      "availableChannel": {
        "@type": "ServiceChannel",
        "serviceUrl": "https://wa.me/59899123456?text=Hola,%20necesito%20un%20cerrajero%20en%20Pocitos",
        "servicePhone": { "@type": "ContactPoint", "telephone": "+59899123456", "contactType": "customer service" },
        "availableLanguage": "es"
      },
      "offers": {
        "@type": "Offer",
        "priceCurrency": "UYU",
        "price": "1900",
        "priceSpecification": { "@type": "PriceSpecification", "minPrice": "1900", "priceCurrency": "UYU" },
        "availability": "https://schema.org/InStock",
        "areaServed": { "@type": "City", "name": "Pocitos" }
      },
      "image": "https://cerrajero.uy/img/cerrajero-pocitos-real.webp",
      "potentialAction": {
        "@type": "CommunicateAction",
        "name": "Escribir por WhatsApp",
        "target": {
          "@type": "EntryPoint",
          "urlTemplate": "https://wa.me/59899123456?text=Hola,%20necesito%20un%20cerrajero%20en%20Pocitos",
          "actionPlatform": ["https://schema.org/MobileWebPlatform", "https://schema.org/DesktopWebPlatform"]
        }
      }
    },
    {
      "@type": "BreadcrumbList",
      "@id": "https://cerrajero.uy/pocitos/#breadcrumb",
      "itemListElement": [
        { "@type": "ListItem", "position": 1, "name": "Inicio", "item": "https://cerrajero.uy/" },
        { "@type": "ListItem", "position": 2, "name": "Montevideo", "item": "https://cerrajero.uy/montevideo/" },
        { "@type": "ListItem", "position": 3, "name": "Pocitos" }
      ]
    },
    {
      "@type": "WebPage",
      "@id": "https://cerrajero.uy/pocitos/",
      "url": "https://cerrajero.uy/pocitos/",
      "name": "Cerrajero en Pocitos – {Marca}",
      "isPartOf": { "@id": "https://cerrajero.uy/#website" },
      "about": { "@id": "https://cerrajero.uy/pocitos/#servicio" },
      "breadcrumb": { "@id": "https://cerrajero.uy/pocitos/#breadcrumb" },
      "dateModified": "{fecha_iso, ej. 2026-09-24}",
      "inLanguage": "es-UY"
    }
  ]
}
</script>
```

Validar en validator.schema.org antes de publicar. No agregar `aggregateRating` ni marcar la reseña de Lucía como `review` (copiada de Google → inelegible y riesgo de acción manual). El `Locksmith` con `@id` `#negocio`, `#website`, dirección de Cordón y `sameAs` va solo en la home (plantilla A).

## 5. Enlaces entrantes a agregar el mismo día [RANKING]

Sin esto la página queda huérfana y no indexa. Mínimo 3 entrantes desde el cuerpo, anchors variados:

| Página | Dónde | Anchor sugerido |
|---|---|---|
| Home `cerrajero.uy/` | Sección "Zonas" (≤ 10–15 anchors visibles) | `cerrajero en Pocitos` |
| `/montevideo/` (madre de departamento) | H3 de la zona con 1–2 frases (tiempo 15–25 min, apertura desde $U 1.900) | `Pocitos: llegamos en 15-25 minutos` |
| `/punta-carretas/` (vecina) | Bloque "También llegamos cerca de…" | `urgencias en Pocitos` |
| `/buceo/` o `/cordon/` (vecina) | Bloque "También llegamos cerca de…" | `también llegamos a Pocitos y Villa Biarritz` |
| `/zonas/` (índice HTML) | Lista completa | `Pocitos` |
| `sitemap-zonas-montevideo.xml` | `lastmod` real de la fecha de publicación | — |

Si `/punta-carretas/`, `/buceo/`, `/parque-batlle/` o `/cordon/` todavía no existen, quitar esos anchors de la sección 12 (no enlazar a 404) y dejar solo los que existan más `/montevideo/`. Disparar IndexNow al publicar; "Solicitar indexación" en GSC solo si es de las 5–10 páginas clave de la tanda.

## 6. Datos que faltan y supuestos

**Variables sin dato del operador (quedan marcadas en el HTML):**

1. `{Marca}` — nombre exacto del negocio (mismo string que en la ficha GBP y el schema de la home). En el JSON-LD también va en `WebPage.name`.
2. `{rating}`, `{n_reseñas}`, `{url_ficha_google}` — línea de prueba del hero y enlace de la reseña de Lucía.
3. `{credencial}`, `{años}`, `{n_trabajos}`, `{garantía}`, `{matrícula / RUT / seguro}` — barra de confianza. Si no existen, borrar el `<li>` correspondiente; no inventar.
4. `{tiempo_trabajo_2}` (cilindro en la rambla, abr-2026) y `{tiempo_trabajo_3}` (llave rota en 26 de Marzo, may-2026) — el operador solo dio el tiempo del trabajo de Benito Blanco.
5. `{precio_llave_rota}` — no hay precio desde para extracción de llave; se dejó como "te lo pasamos por WhatsApp".
6. `{ruta habitual}` — por qué avenidas va de Cordón a Pocitos (el índice de zonas sugiere Av. Brasil / Bulevar España, pero lo tiene que confirmar el operador).
7. `{franja nocturna}` — desde qué hora aplica el +30 %.
8. `{medios de pago}`, `{Garantía sobre el trabajo}`.
9. Fotos reales: `cerrajero-pocitos-real.webp` (hero) y `cerrajero-pocitos-trabajo.webp` (trabajo). Sin foto real, quitar el `<figure>`; nunca poner stock o IA como trabajo hecho.
10. `{fecha_visible}` y `{fecha_iso}` — fecha real de publicación / última edición (guardarla al editar, no `date()` en cada request).

**Supuestos que hay que confirmar antes de publicar:**

- **"24 hs" en title, H1 y description**: se asumió por el tiempo nocturno (30 min) y el recargo +30 %. Si el operador no atiende de madrugada, usar `Cerrajero en Pocitos – Llegamos en 15-25 min desde Cordón` (57) como title, `Cerrajero en Pocitos: llegamos en 15–25 minutos desde Cordón` (60) como H1, y sacar "24 hs" y "las 24 horas" de description, lead y FAQ. **Riesgo**: prometer 24 hs y no cumplirlo = badClicks y reseñas negativas.
- **Fecha de precios "septiembre 2026"**: los precios se dieron hoy sin fecha de vigencia; se fechó con la fecha actual. Cambiarla si son de otro mes.
- **Precios nocturnos calculados** en la FAQ ($U 2.470 y $U 3.640) son 1.900 × 1,3 y 2.800 × 1,3; confirmar que el operador redondea así.
- **URLs de troncales** `/apertura-de-puertas/` y `/cambio-de-cerradura/`: se asumió que existen como páginas de subservicio del EMD. Si no, quitar los `<a>` de los H3 y dejar el texto.
- **Tipo de vivienda y problema típico** se dedujeron de los tres trabajos (edificios de la rambla con cilindro europeo, puerta blindada, llave rota). Si el operador tiene otra lectura de la zona, ajustar el bloque 9.
- **Slug y vecinos** salen de `zonas-rioplatenses.md` (pocitos → punta-carretas, buceo, parque-batlle, cordon). Cordón se incluyó porque además es la base.
- **"Precio confirmado por WhatsApp antes de salir"** en la barra de confianza y en el proceso: sale de la reseña ("precio claro") y de la práctica habitual del nicho; confirmar que el operador lo hace siempre.
- **Cerrajero + Pocitos** aparece 5 veces en texto visible (H1, lead, H2 precios, FAQ, CTA final) más title/description: dentro del rango natural. No agregar más.
