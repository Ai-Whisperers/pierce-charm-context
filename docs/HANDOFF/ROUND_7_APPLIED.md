# Round 7 — Booking + Newsletter + Blog (2026-07-14)

> **Status:** Committed & pushed to `paragu-ai-platform` (commit `e85f4975`).
> **Tests:** All routes 200, build clean (17/17 routes), type-check passes.

---

## W1 — Sistema de reservas con mini-form

**Problema:** el carrito invisible (round 6) sumaba piezas pero el cliente seguía armando el WhatsApp manualmente. Faltaba la pieza que convierte: nombre + fecha + hora.

**Solución:** nuevo `BookingModal.tsx` (modal full-screen) que se abre desde cualquier CTA del sitio. Recolecta:

| Campo | Validación | Requerido |
|---|---|---|
| Nombre | min 2 chars | ✅ |
| Tu WhatsApp | dígitos, formato libre | opcional |
| Fecha | hoy → hoy+60d | ✅ |
| Hora | slots de 12-19 / 9-14 (sáb) | ✅ |
| Servicio | perforación / consulta / joyería / cambio / varios | default: perforación |
| Notas | textarea libre | opcional |

**Output:** mensaje WhatsApp pre-armado con carrito + reserva. Cuando se envía, limpia el carrito.

**Integración:**
- Layout: trigger button "Reservar cita" siempre visible abajo-izquierda (safe-area aware)
- AnatomySwitcher: cada card ahora tiene "+ Lo quiero" mini-button → suma al carrito, y "Reservar este piercing" reemplaza al "Consultar por WhatsApp" cuando hay item activo
- ESC y click en backdrop cierran el modal
- Lock de scroll del body cuando está abierto

**Lo que NO hace (intencional):**
- No guarda reservas en backend (escribimos por WhatsApp). Luana confirma manualmente.
- No bloquea slots específicos — la confirmación es post-WhatsApp.

---

## W2 — Newsletter real con Brevo + fallback

**Problema:** `Newsletter.tsx` solo abría WhatsApp. No capturaba emails. Cero persistencia.

**Solución:** nueva API route `/api/newsletter` con 3 modos:

```
Si BREVO_API_KEY + BREVO_LIST_ID están configuradas:
  → POST a Brevo /v3/contacts con email + nombre + source
  → Si existe (duplicate_parameter) → 200 con "ya estabas suscripta"
  → Si no → crea contacto, agrega a lista

Si Brevo no está configurado (estado actual):
  → Persiste en /tmp/pierce_charm_subscribers.jsonl
  → Devuelve 200 igual (zero-config, recuperable)

Siempre:
  → Valida email (regex)
  → Detecta duplicados últimos 365 días
  → Devuelve debug step-by-step en respuesta (per skill nextjs-backend-patterns)
```

**Componente actualizado:** `Newsletter.tsx` ahora es dual-mode:

- Si el usuario tipea email válido → POST al endpoint → mensaje "¡Anotada!" sin salir de la página
- Si deja email vacío → fallback WhatsApp (mantiene comportamiento anterior)
- Errores de red/API → mensaje inline rojo con el error real

**Para activar Brevo en producción:**
```bash
docker service update pierce-charm_web \
  --env-add BREVO_API_KEY=xkeysib-... \
  --env-add BREVO_LIST_ID=2
```
(Pedir a Luana la API key de Brevo cuando se cree la cuenta — Mailchimp/Buttondown también funcionan cambiando el endpoint.)

---

## W3 — Blog + SEO long-tail

**Problema:** el sitio tenía keywords base en metadata (`layout.tsx`) pero faltaban páginas indexables que ataquen long-tail. Sin blog no hay forma de rankear para queries informacionales.

**Solución:**

### 3.1 — Blog skeleton
- `lib/blog.ts` — parser MD con `gray-matter` (frontmatter) + extract TOC + slugify
- `app/blog/page.tsx` — índice con cards (fecha + tiempo de lectura + excerpt)
- `app/blog/[slug]/page.tsx` — render individual con JSON-LD `Article` schema
- `app/blog/[slug]/BlogPostContent.tsx` — renderer custom (sin librería externa para mantener bundle chico): headings, paragraphs, lists, quotes, code, tables, hr
- Sitemap actualizado con `/blog` + cada post

### 3.2 — 2 posts iniciales
1. **`cuidados-despues-de-un-helix.md`** — 4 min, target query "cuidados helix piercing"
2. **`titanio-vs-acero-quirurgico.md`** — 5 min, target "titanio vs acero piercing", "material piercing Paraguay", "ASTM F136"

Ambos con JSON-LD `Article` schema, OG tags, canonical.

### 3.3 — FAQs adicionales (5)
Añadidas al bloque existente:

| # | Query objetivo | Tipo |
|---|---|---|
| 1 | "cuánto sale un piercing en Asunción" | Pricing |
| 2 | "dónde hacerse septum piercing Asunción" | Local + service |
| 3 | "mejor material para piercing nuevo" | Material |
| 4 | "cambiar joya piercing cicatrizado" | Operación |
| 5 | "elegir joyería segundo piercing" | Compra |

Todas con respuestas que mencionan precios / zonas / materiales específicos de Pierce Charm (no copy genérico). JSON-LD FAQPage se regenera automáticamente.

### 3.4 — Bloque SEO home
Nuevo bloque `seo_long_tail.long_tail_copy` que renderea 3 H3 paragraphs en el home con las keywords más buscadas. Sin afectar el diseño dark/gothic.

### 3.5 — Nav
Nuevo item "Blog" entre "Nosotros" y "Joyería".

---

## Verificación

### Build
```
✓ Compiled successfully in 8.4s
✓ Generating static pages using 7 workers (17/17)
Route (app)
┌ ○ /                          (Static)
├ ƒ /api/newsletter            (Dynamic, server-rendered)
├ ○ /blog                      (Static)
├ ● /blog/[slug]               (SSG, prerendered)
│ ├ /blog/titanio-vs-acero-quirurgico
│ └ /blog/cuidados-despues-de-un-helix
├ ○ /contacto, /eventos, /faq, /galeria, /nosotros, /piercings, /privacidad
├ ○ /robots.txt, /sitemap.xml
└ ○ /terminos
```

### Dev server (port 3001, 3000 estaba ocupado)
```
/                                            : 200 147553B
/blog                                        : 200 119573B
/blog/cuidados-despues-de-un-helix           : 200 134083B
/blog/titanio-vs-acero-quirurgico            : 200 140483B
/faq                                         : 200 144628B
/piercings                                   : 200 152931B
/contacto                                    : 200 121094B
/sitemap.xml                                 : 200 1657B (incluye /blog + 2 posts)
```

### API newsletter
```
POST /api/newsletter (valid)    → 200 {ok:true, message:"¡Suscripta!"}
POST /api/newsletter (duplicate)→ 200 {ok:true, message:"Ya estabas suscripta"}
POST /api/newsletter (invalid)  → 400 {error:"Email inválido"}
GET  /api/newsletter            → 200 {ok:true, provider:"local-only"}
```

JSONL persistido: `/tmp/pierce_charm_subscribers.jsonl` (en el container).

---

## Pendiente para Luana (no bloquea)

| # | Pendiente | Bloquea | Cuándo |
|---|---|---|---|
| 1 | Foto de Luana (sonriendo, piercings visibles, outfit) | Lanzamiento | Esta semana |
| 2 | WhatsApp real del estudio | Lanzamiento | Cuando tenga línea |
| 3 | @pierce.charm en IG | Lanzamiento | Cuando lo cree |
| 4 | Email público + RUC | Lanzamiento | Cuando los tenga |
| 5 | Dirección del estudio | GMB setup | Cuando tenga local |
| 6 | Logo formal (Luana diseña) | Identidad | Cuando lo tenga |
| 7 | Brevo API key | Newsletter real (vs local) | Cuando cree cuenta |

## Pendiente técnico (cuando sea)

- **W1**: Confirmación automatizada de cita con Google Calendar (cuando Luana decida calendario)
- **W1**: SMS/email recordatorio 24h antes (cuando tenga base de datos de clientes)
- **W2**: Dashboard para ver suscriptores (cuando Brevo esté conectado)
- **W3**: 2da ronda de posts: "Cómo elegir tu primer piercing", "Titanio vs oro", "Cuidados del septo", "Qué esperar el día de tu cita"

---

*Round 7, Erebus, 2026-07-14. Total invertido: ~3h. Commit: `e85f4975` en `paragu-ai-platform`.*