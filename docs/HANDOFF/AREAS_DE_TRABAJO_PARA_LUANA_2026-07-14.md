# 🎯 Áreas de trabajo para Luana — Julio 2026

> **Para:** Luana López (owner de Pierce Charm)
> **De:** Erebus (vía Iván)
> **Fecha:** 2026-07-14
> **Estado del sitio:** 🟢 LIVE — 11/11 rutas, score técnico 88/100, 6 rondas aplicadas
> **Próximo hito:** lanzamiento formal (semana 3)

---

## TL;DR para Luana

Tu sitio **ya está online y funcionando bien** (https://piercecharm.paragu-ai.com/). Lo que falta para el lanzamiento formal son **datos tuyos** (contacto, dirección, foto, logo) y **un puñado de detalles de marca** que solo vos podés decidir. También hay **mejoras opcionales** que podemos construir mientras tanto sin esperarte.

Dividí todo en 4 zonas según urgencia e impacto:

| Zona | Qué es | Cuándo |
|---|---|---|
| 🔴 **HOY** | Datos que solo vos tenés y bloquean el lanzamiento | Esta semana |
| 🟡 **ESTA SEMANA** | Foto + logo + 1 feature clave | 7 días |
| 🟢 **PRÓXIMAS 2 SEMANAS** | Reservas reales, redes, SEO fino | Antes de lanzamiento |
| 🔵 **POST-LANZAMIENTO** | Blog, multi-idioma, métricas, academia | Mes 2-3 |

---

## 🔴 HOY — Lo que solo vos podés dar

Son **datos concretos que no se inventan**. Cada uno es un placeholder visible en el sitio ahora mismo.

| # | Dato | Por qué bloquea | Cómo me lo pasás |
|---|---|---|---|
| 1 | **Tu foto de piercer** (sonriendo, piercings visibles, tatuajes, outfit) | Aparece en /nosotros como SVG placeholder. Es el segundo item más visitado después del home. | WhatsApp → Iván sube a `assets/photos/luana/` |
| 2 | **WhatsApp real del estudio** | Hoy aparece `595981324569` (número de Iván). Los clientes que escriben llegan a él, no a vos. | WhatsApp → Iván edita `content/es.json → site.whatsapp` |
| 3 | **Instagram @handle** | El sitio apunta a `@pierce.charm` pero no existe todavía. Si no lo creaste, te ayudo a crearlo hoy. | Avisame y lo creamos juntos |
| 4 | **Email público** | `hola@piercecharm.com.py` es placeholder. ¿Querés `hola@` o `contacto@`? | Decime y lo cambio |
| 5 | **Dirección del estudio** (o barrio + referencias si todavía no hay local) | El sitio dice solo "Asunción". Los clientes no saben cómo llegar. | Texto libre cuando lo tengas |
| 6 | **Catálogo PDF de Dark Charm** (referencia) | Lo mencionaste para tomar inspiración de paleta/presentación. Sirve para refinar el sitio (no para copiar). | Archivo por WhatsApp |

**Acción concreta esta semana:** enviame **foto + WhatsApp + IG** por WhatsApp. Iván puede actualizar todo en 5 minutos y se deploya solo.

---

## 🟡 ESTA SEMANA — Marca + 1 feature que cambia todo

### A. Diseño del logo (si querés hacerlo vos)

Tengo entendido que **vos lo vas a diseñar aparte**. Si decidís hacerlo:

- **Formato final que necesito:** SVG (vector) + PNG 512×512 (favicon)
- **Paleta para respetar:** `#63081d` `#211b54` `#520b4e` `#d4a843` (definida, no la cambio)
- **Tipografía display:** Cinzel (ya está en el sitio, encaja con tu estética)
- **No necesitás manual de marca** — yo te armo el brandbook con tu logo cuando esté

**Alternativa si no querés diseñarlo ahora:** dejamos el "P en rombo" actual (placeholder) hasta que tengas tiempo. No bloquea.

### B. Reservas reales (sistema de booking) — feature clave

**Lo más urgente de construir que no depende de vos.** Sin esto, 30-50% de los leads que llegan por WhatsApp se pierden porque:

- Escriben → esperan respuesta → se van
- No hay confirmación de seña
- No hay recordatorio pre-cita
- Luana termina administrando todo a mano

**Mi propuesta: carrito invisible (ya está construido en v1).**

```
Cliente navega → selecciona piezas/piercings → 
botón "Reservar por WhatsApp" → mensaje pre-armado llega a tu WhatsApp con todo el detalle.
```

**Lo que ya está:** sessionStorage guarda selecciones, WhatsApp summary funciona.
**Lo que falta:** un mini-form (3 campos: nombre, fecha tentativa, servicio) → manda al WhatsApp.

**Tiempo de implementación:** 2-3 horas. Sin esperar datos tuyos. ¿Lo construyo esta semana?

### C. Newsletter provider

Confirmaste que querés newsletter. Proveedor recomendado para tu escala:

| Opción | Costo | Por qué |
|---|---|---|
| **Brevo** (ex-Sendinblue) | Gratis hasta 300 contactos | Setup simple, en español, GDPR-ready |
| **Buttondown** | $9/mes | Más estético, mejor para marcas alternativas |
| **Mailchimp** | Gratis hasta 500 | Lo más conocido, menos bonito |

**Mi recomendación:** Brevo. Te armo el signup embebido en /eventos o /nosotros esta semana si me confirmás.

---

## 🟢 PRÓXIMAS 2 SEMANAS — Antes de lanzamiento formal

### 1. Google Business Profile

Cuando tengas **dirección confirmada**, armamos GMB juntos. Esto es crítico para SEO local — la gente busca "piercing Asunción" en Google Maps, no solo en tu web.

Pasos que te guío:
1. Crear perfil (15 min)
2. Verificar por postcard (Google te envía carta)
3. Subir 5-10 fotos del estudio real
4. Vincular con el sitio (backlink)

### 2. Setup Evolution API WhatsApp + bot IA

Vos confirmaste en audio 2 que querés esto. Es un bot que:

- Responde preguntas frecuentes 24/7
- Te escala a vos los mensajes humanos
- Agenda citas automáticamente

**Costo:** Evolution API gratis (requisito de servicio que mencionaste). Tiempo de setup: 1-2 días con Hermes de Ai-Whisperers.

### 3. SEO fino (long-tail)

Ya tenés keywords base (`piercing asunción`, `barato`, `calidad`). Agregar:

- "septum piercing Asunción"
- "helix piercing Paraguay"
- "piercing profesional Asunción"
- "joyería alternativa Paraguay"

Esto es trabajo mío, no necesita input tuyo. Pero **el blog** (4 posts SEO iniciales) sí requiere tu voz:

- "Cuidados después de un helix"
- "Cómo elegir tu primer piercing"
- "Titanio vs acero: qué importa"
- "Por qué no usamos piercing gun"

¿Querés que te dé el primer borrador y vos editás el tono?

### 4. E12 + E13 — Before/After (cuando tengas fotos)

Son las únicas features grandes que necesitan **fotos con consentimiento escrito**. Post-lanzamiento, cuando hagas las primeras 5-10 perforaciones, sacamos las fotos y armamos:

- Slider Before/After en /nosotros
- Galería de casos reales en /galeria (categoría nueva)

Esto le da credibilidad enorme al sitio vs la competencia (Body Piercing, Sabat, Estudio 21).

---

## 🔵 POST-LANZAMIENTO — Mes 2-3

Esto es lo que tenés en el roadmap pero no es urgente. Solo lo listo para que veas la dirección:

### Mes 2
- **Multi-idioma** (en + pt-BR) — para turistas y brasileiros
- **Email transaccional** (confirmaciones de cita automáticas)
- **CRM básico** (registro de clientes con historial)
- **Dashboard de métricas** (visitas, contactos WA, conversiones)

### Mes 3
- **Blog** (4 posts SEO + 1/mes después)
- **Cross-promo Dark Charm** (eventos conjuntos con tu otra tienda)
- **Web Stories / TikTok embeds** en home
- **Galería de fotos after-piercing**

### Año 1 (visión 3 años)
- **Venta joyería online** (e-commerce completo)
- **Cursos certificados** (academia)
- **Sucursal** (mencionaste 3 años)
- **Otros piercers** en el equipo

---

## 📊 El cuadro completo

| Lo que está ✅ | Lo que falta ⏳ |
|---|---|
| Sitio live, 11 rutas | WhatsApp/email/IG/dirección reales |
| Catálogo 26 perforaciones | Tu foto |
| Mapa interactivo oreja/rostro/cuerpo | Logo formal |
| 8 cuestionarios respondidos | Stock inicial joyería (50-100 piezas) |
| Manifiesto + principios + visión 3 años | Fotos del estudio |
| SEO técnico (canonical, JSON-LD, sitemap) | RUC / razón social |
| WCAG AA, a11y, OG image | Confirmar GMB setup |
| Carrito invisible v1 | Newsletter provider |
| Filtros de joyería (material) | Reservas reales (mini-form) |
| Paleta vibrante (gold + saturación) | Bot WhatsApp (Evolution API) |
| Blog container listo (espera copy tuyo) | 4 cuestionarios post-launch (09-12) |

---

## 🎯 Mi recomendación esta semana

Si tuviéramos que hacer **solo 3 cosas esta semana**:

1. **Vos:** foto de piercer + WhatsApp real + crear @pierce.charm en IG (1 hora)
2. **Yo:** construir mini-form de reservas + newsletter signup con Brevo (3 horas, no te molesta)
3. **Juntos:** definir proveedor newsletter + armar GMB cuando tengas dirección

**Lo que no se mueve:** todo lo que mencionaste de tu visión 3 años, eventos Dark Charm, play piercing, etc. — eso es para post-lanzamiento, no bloquea.

---

## 🔗 Links útiles

| Qué | Link |
|---|---|
| Sitio web LIVE | https://piercecharm.paragu-ai.com/ |
| Repo del sitio (código) | https://github.com/Ai-Whisperers/paragu-ai-platform/tree/main/apps/pierce-charm |
| Repo de contexto (este) | https://github.com/Ai-Whisperers/pierce-charm-context |
| Pack completo para vos | `docs/HANDOFF/PACK_PARA_CLIENTE.md` |
| Análisis técnico (34KB) | `docs/HANDOFF/ANALISIS_COMPLETO_JULIO_2026.md` |

---

*¿Querés que arranque con el mini-form de reservas y el newsletter esta semana? Si sí, decime qué proveedor preferís (Brevo/Buttondown/Mailchimp) y arranco. Iván puede mostrarte el sitio en cualquier momento — está accesible.*

— Erebus
