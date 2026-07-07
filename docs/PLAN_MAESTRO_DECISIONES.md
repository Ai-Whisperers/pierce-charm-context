# 🎯 PLAN MAESTRO DE DECISIONES — Pierce Charm

> **Cada item tiene:** código único, descripción, categoría, prioridad, owner, blockers, status.
> **Consumo:** Erebus lo consulta antes de cada cambio significativo; Iván/Ellos lo usan para coordinar.

---

## Cómo leer este plan

- **Prioridad:** **P0** = bloquea lanzamiento · **P1** = bloquea post-lanzamiento formal · **P2** = nice-to-have · **P3** = backlog
- **Owner:** **Erebus** (desarrollo en código) · **Iván** (operación/coordinación) · **Luana** (cliente)
- **Status:** ⏳ pendiente · 🔄 en curso · ✅ done · ❌ blocked · 💤 abandoned
- **Blocked by:** lo que necesita para ejecutarse

---

## SECCIÓN A — DECISIONES DE DISEÑO Y CÓDIGO APLICADAS

### D1 ✅ — Paleta gothic
- Paleta 3 HEX + gold accent
- Aplicada en :root via tokens + Tailwind v4
- **Commit:** `151fbac`

### D2 ✅ — Mapa interactivo de oreja con hotspots
- Componente EarAnatomy con 14 hotspots clickeables
- **Commit:** `151fbac`

### D3 ✅ — Piercings con niveles 1/2/3
- Cada piercing tiene level 1/2/3 según complejidad
- **Commit:** `151fbac`

### D4 ✅ — Decoraciones SVG inline (no imágenes)
- 9 ornamentos en components/ornaments.tsx
- **Commit:** `151fbac`

### D5 ✅ — Fonts Cinzel + Tangerine + Inter
- Display: Cinzel (Roman caps) · Script: Tangerine · Body: Inter
- **Commit:** `151fbac`

### D6 ✅ — Cruces invertidas como niveles
- Ornament CrossInverted usado como icon de nivel en catálogos
- **Commit:** `151fbac`

### D7 ✅ — WhatsApp como CTA principal
- whatsappUrl() helper, todos los links pasan por él
- **Commit:** `151fbac` + `cbf3b79`

### D8 ✅ — Sin blog ni tienda online (MVP)
- Sitio solo catálogo/mostrar (no e-commerce)
- **Estado:** el catálogo se quedó en 1 página con tabs por categoría
- **Commit:** `151fbac`

### D9 ✅ — `experimental.globalNotFound: false`
- Workaround para Next 16 bug
- **Aplica hasta que Next 16 fixe el upstream bug**

### D10 ✅ — Data-driven: 0 hardcoded en JSX
- lib/site-config.ts helper + todos los phones via contenido
- **Commit:** `151fbac`

### D11 ✅ — Sitemap dinámico
- app/sitemap.ts reemplaza el 404 anterior
- **Commit:** `151fbac`

### D12 ✅ — OG image + Twitter card
- 1200×630 PNG + meta tags
- **Commit:** `151fbac`

### D13 ✅ — WCAG AA contrast (gold + primary-light)
- Gold #b08838 → #d4a843, primary-light #8b1a31 → #b2364f
- **Commit:** `151fbac`

### D14 ✅ — Privacy + Terms en español (Ley 6534 PY)
- /privacidad y /terminos completas
- **Commit:** `151fbac`

### D15 ✅ — Cookie banner con localStorage opt-in
- components/CookieBanner.tsx
- **Commit:** `151fbac`

### D16 ✅ — Skip-to-content + ARIA
- sr-only focus:not-sr-only en <a>
- aria-current, aria-expanded, aria-hidden en nav
- **Commit:** `151fbac`

### D17 ✅ — /piercings?pin=daith persiste selección
- useSearchParams wrapped en Suspense
- **Commit:** `151fbac`

### D18 ✅ — CI/CD vía GitHub Actions central.yml
- Auto-deploy on push a main
- **Commit:** `151fbac`

### D19 ✅ — Manifiesto + principles en /nosotros
- 6 principles: bioseguridad, curaduría, espacio seguro, comunidad, sustentabilidad, antipatriarcado
- **Commit:** `f58c027`

### D20 ✅ — Banner ticker rotativo
- 4 mensajes alternativos rotando cada 5s
- **Commit:** `f58c027`

### D21 ✅ — Visión 3 años en /nosotros
- 4 quarters (en 1 / en 2 / en 3 / futuro)
- **Commit:** round_3 (pendiente commit)

### D22 ✅ — Diferenciador "Honestidad sobre tu anatomía"
- En home + /nosotros
- **Commit:** round_3

### D23 ✅ — Piercer Luana López surfacing
- Bloque nosotros.piercer
- **Commit:** round_3

### D24 ✅ — Renombre galería (Sepultura → Alternative, Plugs → Expansores)
- Categorías del sitio + items
- **Commit:** round_2 + round_1

### D25 ✅ — Catálogo reescrito (26 perforaciones, precios 50/100/150K)
- Categorías 5: Básicos, Cartílago, Faciales, Body, Industrial/orbital
- Removidos: surface, microdermal, thermal, expansiones, nipple
- **Commit:** `cbf3b79`

### D26 ✅ — Horarios reales L-V 12-20 / Sáb 9-15 / Dom Cerrado
- **Commit:** `cbf3b79`

### D27 ✅ — "Joyería curada" → "Joyería alternativa"
- 2 lugares (home.features + nosotros.values)
- **Commit:** `cbf3b79`

### D28 ✅ — /eventos page con placeholder honesto + lista de sumar
- **Commit:** round_3 (UI) — pendiente commit

### D29 ✅ — Testimonios section con placeholder honesto
- components/Testimonials.tsx
- **Commit:** round_3 — pendiente commit

### D30 ✅ — Newsletter config
- data/newsletter + cta por WhatsApp (sin provider backend por ahora)

### D31 ✅ — Reviews CTA + post-cita microcopy
- data/reviews + URL pendiente hasta GMB exista

### D32 ✅ — SEO local keywords en metadata
- piercing asunción / barato / calidad + variety
- site.seo.local_keywords

### D33 ✅ — Feriados paraguayos pendientes de config
- Para automatizar la estrategia de content

---

## SECCIÓN B — DECISIONES DE UX PENDIENTES (E1-E16)

### E1 🔄 — Bajar el CTA "Reservar" del home
**Decisión:** cambiar para que el cliente descubra scroleando.
**Trade-off:** baja conversión directa / aumenta engagement del catálogo.
**Bloqueado por:** confirmación de Iván.
**Owner:** Erebus (implementación) · Iván (decisión).

### E2 🔄 — Sección editorial "Donde el cuerpo se vuelve lienzo"
**Decisión:** agregar párrafo de profundidad sobre historia/ significado de los piercings.
**Trade-off:** +2 min de lectura / mayor conexión emocional.
**Bloqueado por:** copy de Luana.
**Owner:** Luana (copy) · Erebus (UI).

### E3 ✅ — Renombrar "Joyería curada" (ya hecho en C1)
**Decisión:** "Joyería alternativa" — DONE.

### E4 ✅ — Renombre "Sepultura & Góticos" → "Alternative style" (D24)
**Decisión:** ya hecho.

### E5 ✅ — Renombre "Plugs & Túneles" → "Expansores" (D24)
**Decisión:** ya hecho.

### E6 🔄 — Mapa de oreja: hover con foto o highlight color
**Decisión:**
- Sin fotos hoy: tooltip + highlight color
- Con fotos: hover muestra foto real
- Si cliente prefiere solo highlight color → bloquear ascenso a foto de fondo
**Bloqueado por:** feedback de Luana + fotos reales.
**Owner:** Luana (decisión) · Erebus (UI condicional).

### E7 🔄 — Catálogo separado o toggle perforaciones/joyería
**Decisión:** separar en /piercings + /joyeria (4h) o toggle en /galeria (1h).
**Trade-off:** SEO +1 página vs UX simpler.
**Bloqueado por:** decisión de Iván.
**Owner:** Iván (decisión) · Erebus (implementación).

### E8 💤 — Filtros de joyería (material + color + zona)
**Decisión:** feature pospuesta. **MVP=sin filtros**; agregar cuando llegue stock.
**Trigger:** cuestionario 09 completado (cuando el cliente compre stock).
**Owner:** Erebus.

### E9 ✅ — CTA "Solicitar presupuesto" en lugar de "Reservar"
**Decisión:** aplicado. `/galeria` y cards de piercing usan "Solicitar presupuesto".

### E10 ✅ — Banner ticker deco (D20)
**Decisión:** hecho en home, 4 mensajes rotando.

### E11 ✅ — /nosotros "principios" en vez de "bioseguridad repetido"
**Decisión:** hecho. Principles block reemplaza values repetido.

### E12 💤 — Before/After en /nosotros
**Decisión:** placeholder honesto hasta tener fotos de clientes reales.
**Trigger:** cuestionario 08 (after photos con consentimiento).

### E13 💤 — /nosotros: experiencias vs estudio
**Decisión:** arrancamos con "experiencias del estudio" (placeholders de SVG) y reemplazamos con fotos cuando existan.
**Trade-off:** fotos del local cuando exista vs fotos de personas (después).
**Bloqueado por:** estudio físico existente + fotos.
**Owner:** Luana (when study exists) · Erebus (UI after photos arrive).

### E14 🔄 — CTA fijo en navbar
**Decisión:** el "Reservar" actual cumple + "Solicitar presupuesto" en cards. ¿Otro más?
**Trade-off:** más botones = más clara intención vs distracción visual.
**Bloqueado por:** feedback.
**Owner:** Iván · Erebus.

### E15 💤 — Carrito invisible → WhatsApp summary
**Decisión:** MVP2. Triggered when: inventario cargado +Luana decide habilitar.
**Owner:** Erebus.
**Estimación:** 1-2 semanas.

### E16 ✅ — Manifesto en /nosotros (LGBTQ+, antipatriarcal, etc.)
**Decisión:** hecho. Ver D19.

### C1-C8 ✅ — Cambios de copy
- Todos aplicados.

### U1-U4 🔄 — UX improvements menores
- U1 ✅ Hover muestra nombre del piercing en el mapa (tooltip)
- U2 ⏳ Carrito invisible (mismo que E15)
- U3 ✅ Click directo a WhatsApp con mensaje auto
- U4 ✅ WhatsApp con número visible + mensaje claro

---

## SECCIÓN C — DATOS DEL CLIENTE PENDIENTES

### C01 ❌ — WhatsApp real del estudio
**Bloqueado por:** el cliente aún no gestiona este dato.
**Acción:** Ivan solicitar al cliente cuando esté listo.
**Impacto:** afecta todos los botones WA del sitio.

### C02 ❌ — Email público
**Bloqueado por:** cliente.
**Impacto:** layout metadata + redirección desde Footer.

### C03 ❌ — Instagram handle
**Bloqueado por:** cliente (creará hoy/jueves).
**Impacto:** link en Footer, contacto, Open Graph updated.
**Acción cuando:** el cliente confirme → Ivan agregar al es.json.

### C04 ❌ — TikTok handle
**Bloqueado por:** cliente.
**Impacto:** opcional, agregar a Footer si tienen.

### C05 ❌ — Facebook URL
**Bloqueado por:** cliente.
**Impacto:** link en Footer.

### C06 ❌ — Dirección real del estudio
**Bloqueado por:** cliente (no tiene estudio todavía).
**Impacto:** contacto, JSON-LD LocalBusiness.
**Acción cuando:** exista dirección real → actualizar contacto.address + mapa iframe.

### C07 ❌ — RUC / razón social
**Bloqueado por:** cliente (no la ha tramitado).
**Impacto:** factura + Footer legal + privacy policy oficial.
**Documento:** cuestionario 10.

### C08 ⏳ — Foto del piercer (Luana)
**Estado:** Luana se toma esta semana.
**Acción:** Ivan recibe foto → Erebus reemplaza `<nosotros>.piercer.foto_url` placeholder.
**Formatos aceptados:** JPG/WebP/PNG.

### C09 ❌ — Foto del estudio
**Bloqueado por:** estudio no existe aún.
**Acción:** reprogramar.

### C10 ⏳ — Logo formal
**Estado:** Luana lo diseña aparte (ella es diseñadora).
**Owner:** Luana.
**Acción:** Cuando esté lista, Ivan recibe archivos → Erebus reemplaza favicon-master.svg + actualiza Header.tsx + actualiza og.png.

### C11 ❌ — Catálogo PDF de joyería (referencia)
**Bloqueado por:** amiga de Luana no lo pasó aún.
**Acción:** Ivan pedir a Luana.

### C12 ❌ — Fotos reales de inventario de joyería
**Bloqueado por:** inventario aún no comprado.
**Documento:** cuestionario 09.

---

## SECCIÓN D — EVENTOS Y OPERACIONES

### E-EV1 ⏳ — Setup Google Business Profile
**Trigger:** cuando exista dirección física confirmada.
**Owner:** Luana (cuenta) + Iván (technical help).
**Documento:** cuestionario 12.

### E-EV2 ⏳ — Setup Evolution API WhatsApp
**Trigger:** cuando se decida automatizar triage con bot.
**Estimación:** 30 min de setup técnico.
**Owner:** Erebus.

### E-EV3 ⏳ — Newsletter provider (Mailchimp / Brevo / Buttondown)
**Trigger:** cuando se decida arrancar email marketing.
**Owner:** Iván + Erebus.

### E-EV4 ⏳ — Permitir reviews en Google (botón clickable post-cita)
**Trigger:** cuando tengamos URL real de GMB.
**Documento:** cuestionario 12.

### E-EV5 ⏳ — Estrategia 100 posts (contenido IG)
**Trigger:** cuando se cree la cuenta.
**Owner:** Luana (create) + Erebus (lista inicial con research).
**Acción:** generar lista de 100 ideas con holidays PY + contenido recurrente.

### E-EV6 ⏳ — Eventos Dark Charm cross-promo
**Estado:** Luana tiene el negocio Dark Charm (ropa alternativa + accesorios).
**Acción:** documentar la marca + posible colaboración.
**Owner:** Luana.

### E-EV7 ⏳ — Percer admirado (hand-free)
**Estado:** Luana dijo "voy a anotar el nombre" (no llegó).
**Owner:** Luana.
**Acción:** agregar a research y (si aplica) a /nosotros.

---

## SECCIÓN E — POST-LANZAMIENTO (BACKLOG P2-P3)

### P2.1 💤 — Sistema de reservas con calendario (Cal.com o similar)
**Documento:** backlog.
**Estimación:** 1 semana.

### P2.2 💤 — Blog con 4 posts SEO iniciales
- "Cuidados post-piercing" (ya 90% escrito)
- "Cómo elegir tu primer piercing"
- "Cómo verificamos la calidad de la joyería"
- "Historia del piercing alternativo"
**Estimación:** 4-8 horas.
**Owner:** Erebus (escribir) + Luana (revisar tono).

### P2.3 💤 — Multi-idioma (es-PY + en + pt-BR)
**Estimación:** 1 semana.
**Owner:** Erebus.

### P2.4 💤 — Email transaccional (confirmaciones de cita)
**Estimación:** 2-3 días.

### P2.5 💤 — CRM básico + tracking de conversiones WhatsApp
**Estimación:** 1-2 semanas.

### P2.6 💤 — Galería de fotos after-piercing (con consentimiento)
**Trigger:** cuando haya 5+ fotos con consentimiento.
**Estimación:** 1 día.

### P2.7 💤 — Web Stories / TikTok embeds en home
**Trigger:** cuando existan las cuentas.
**Estimación:** 1-2 días.

### P2.8 💤 — Dashboard de métricas (visitas, contactos WA, conversiones)

### P3.1 💤 — Analytics: ¿Google Analytics o Plausible/Fathom?
**Owner:** Iván.

### P3.2 💤 — SEO internacional ("best piercing Asunción" en inglés)

### P3.3 💤 — Convención tatuajes/piercings — presencia institucional
