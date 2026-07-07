# 📦 PACK PARA LUANA — Pierce Charm

> **Para:** Luana López (diseñadora/contractor) **y** Ivan (operador Ai-Whisperers)
> **De:** Erebus
> **Cuándo:** 2026-07-07
> **Qué:** Sitio web + cuestionarios para que el cliente responda + roadmap hasta lanzamiento

---

## 🌐 Lo que ya está online (LIVE)

**Sitio web del cliente:** **https://piercecharm.paragu-ai.com/**

| Ruta | Status | Tamaño |
|---|---|---|
| `/` Home con hero gothic | ✅ 200 | 96 KB |
| `/piercings` Catálogo interactivo (36 perforaciones con ear map SVG) | ✅ 200 | 52 KB |
| `/galeria` Joyería alternativa | ✅ 200 | 96 KB |
| `/nosotros` Sobre el estudio | ✅ 200 | 79 KB |
| `/contacto` WhatsApp + horarios | ✅ 200 | 77 KB |
| `/faq` 8 preguntas accordion | ✅ 200 | 81 KB |
| `/privacidad` Política de privacidad (Ley 6534 PY) | ✅ 200 | 59 KB |
| `/terminos` Términos y condiciones | ✅ 200 | 57 KB |
| `/sitemap.xml` | ✅ 200 | (ya estaba 404 — arreglado) |
| `/og.png` 1200×630 | ✅ 200 | 170 KB |
| `/favicon.svg`, `/apple-touch-icon.png`, etc. | ✅ 200 | multi-tamaño |
| `/manifest.json` PWA | ✅ 200 | |

**Tiempo de respuesta:** ~85 ms Paraguay → VPS Paraguay (Cloudflare proxy)

---

## 📋 Cuestionarios para el cliente (8 sesiones, ~215 preguntas)

**Ubicación en el context repo:** `docs/08_questionnaires/`

**Links directos (raw github) — copiá y pegá en WhatsApp o email:**

| # | Tema | Link al cuestionario |
|---|---|---|
| 01 | Datos básicos del estudio (horarios, WhatsApp, IG, email, dirección, modalidad de reserva) | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/01_datos_basicos_estudio.md |
| 02 | Catálogo de piercings (27 tipos con precio, materiales, calibres) | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/02_catalogo_piercings.md |
| 03 | Joyería y catálogo curado | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/03_joyeria_catalogo.md |
| 04 | Bioseguridad y procesos (autoclave, instrumental, cuidados) | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/04_bioseguridad_procesos.md |
| 05 | Estética, marca y tono | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/05_estetica_marca_y_tono.md |
| 06 | Clientes y operaciones (CRM, conflictos, idioma) | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/06_clientes_y_operaciones.md |
| 07 | Marketing, redes y competencia | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/07_marketing_redes_competencia.md |
| 08 | Fotos y assets (fotos estudio, piercer, joyería, logo) | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/08_fotos_y_assets.md |

**Cómo usarlo:** Ivan envía **UNO por día** al cliente por WhatsApp. El cliente responde. Ivan anota las respuestas en el `.md` correspondiente y actualiza el `STATUS.md`.

---

## 🗂️ Repos separados (lo que acordamos)

### Repo 1: Sitio web

- **Path en monorepo:** `Ai-Whisperers/paragu-ai-platform/apps/pierce-charm/`
- **URL GitHub:** https://github.com/Ai-Whisperers/paragu-ai-platform/tree/main/apps/pierce-charm
- **Commits relevantes:**
  - `f8ccc2f` — fix Dockerfile.standalone syntax error
  - `151fbac` — Roast Round 1 (data-driven + sitemap + OG + FAQ schema + 36 piercings + WCAG + privacy + terms + CI/CD)

### Repo 2: Context (este repo)

- **Path:** `Ai-Whisperers/pierce-charm-context/`
- **URL GitHub:** https://github.com/Ai-Whisperers/pierce-charm-context
- **Estructura:**
  ```
  docs/
    01_brief/                      ← brief original
    02_meetings/                   ← notas de reuniones
    03_research/                   ← research (catalogo piercings)
    04_decisions/                  ← decisiones D1-D9
    05_brand/                      ← paleta, tipografía, assets
    06_competitors/                ← análisis competitivo
    07_backlog/                    ← TODO post-lanzamiento
    08_questionnaires/             ← los 8 cuestionarios + STATUS
    HANDOFF/                       ← este pack y otros deliverables
    ATTRIBUTIONS.md                ← open source licenses
  assets/                          ← logos, fotos, mood board (placeholders)
  README.md
  CHANGELOG.md
  ```

---

## 🔧 Detalles técnicos

- **Stack:** Next.js 16.2 + Tailwind v4 + TypeScript + pnpm
- **Tema:** Modo oscuro gothic con 3 HEX `#63081d` `#211b54` `#520b4e` + gold decorativo `#d4a843`
- **Tipografía:** Cinzel (display) + Tangerine (script) + Inter (body) via Google Fonts
- **Container:** Docker Swarm en `72.61.44.159` (Hostinger VPS), Traefik + Cloudflare proxy
- **CI/CD:** GitHub Actions matrix + auto-deploy (push a `main` → build → deploy)
- **Imagen final:** 199 MB (Node 22 alpine + .next/standalone)
- **Repo:** privado (Ai-Whisperers org)

### Decisiones técnicas (D1-D9 en detalle)

| # | Decisión | Razón |
|---|---|---|
| D1 | Modo oscuro único | Los 3 HEX son oscuros |
| D2 | Mapa interactivo de oreja con hotspots | Pedido del cliente: "presupuestar cita" |
| D3 | Piercings con niveles 1/2/3 | Para que el cliente entienda qué implica cada uno |
| D4 | Decoraciones SVG inline (no imagen) | Escalan sin pixelarse, colores vía CSS vars |
| D5 | Cinzel + Tangerine + Inter | Transmite dark/gothic sin caer en clichés |
| D6 | Cruces invertidas como indicador de nivel | Reusa ornamento ya presente |
| D7 | WhatsApp como CTA principal en todas partes | El cliente gestiona todo por WhatsApp |
| D8 | Sin blog ni tienda online | El sitio es para mostrar catálogo, no e-commerce |
| D9 | `experimental.globalNotFound: false` | Workaround para bug de Next 16 |

---

## ⚠️ Lo que falta del cliente (bloquea lanzamiento formal)

**El sitio YA está online y funcional**, pero tiene placeholders en estos datos:

| Dato | Estado actual | Necesitamos |
|---|---|---|
| WhatsApp | `595981324569` (Ivan) | Número del estudio |
| Instagram | `@pierce.charm` (placeholder) | Handle real |
| Email | `hola@piercecharm.com.py` (falso) | Email real |
| Dirección | "Asunción, Paraguay" | Barrio + referencias |
| Horarios | Mar-Sáb 14:00-20:00 (placeholder) | Horarios reales |
| Precios | rango Gs 80.000 - Gs 250.000 | Ajustar según cuestionario 02 |
| Fotos del estudio | placeholders SVG | Fotos reales (cuestionario 08) |
| Fotos del piercer | placeholder SVG | Foto real |
| Foto de joyería | placeholders SVG "Foto pendiente" | Fotos reales (cuestionario 08) |
| Logo | letra "P" en rombo | Logo real (Luana puede diseñar) |

**Cómo se actualiza:** Editar `apps/pierce-charm/content/es.json` → push a `main` → CI/CD rebuild + redeploy automático. Sin intervención manual.

---

## 🎯 Roadmap recomendado

### Esta semana
1. **Luana diseña el logo** (si quieren, va como trabajo aparte de diseño, ~3-5 días)
2. **Ivan envía cuestionario 01** al cliente por WhatsApp
3. **Cliente responde cuestionario 01** (datos básicos)
4. Ivan actualiza `content/es.json` → push → auto-deploy

### Semana 2
5. Ivan envía cuestionarios 02-04 (catálogo + bioseguridad)
6. Cliente responde → Ivan aplica cambios
7. **Si el cliente envía fotos en cuestionario 08** → Ivan sube a `public/photos/` y reemplaza los SVG placeholders

### Semana 3 (lanzamiento formal)
8. Logo + fotos + datos reales → sitio 100% production-ready
9. SEO submit: Google Search Console + Bing Webmaster
10. Privacy + Terminos ya están

### Post-lanzamiento (backlog)
- Sistema de reservas con calendario embed (Cal.com)
- Multi-idioma (en + pt-BR para turistas)
- Blog con 4 posts SEO iniciales
- Email transaccional para confirmaciones
- CRM básico + tracking de conversiones WhatsApp

---

## 🔗 Links útiles

| Qué | Link |
|---|---|
| Sitio web LIVE | https://piercecharm.paragu-ai.com/ |
| GitHub sitio web (apps/pierce-charm) | https://github.com/Ai-Whisperers/paragu-ai-platform/tree/main/apps/pierce-charm |
| GitHub contexto del cliente | https://github.com/Ai-Whisperers/pierce-charm-context |
| Cuestionarios (índice) | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/README.md |
| Documentación interna Ai-Whisperers | https://hermes-agent.nousresearch.com/docs |

---

## 📞 Quién hace qué

- **Luana:** diseñar logo si quieren + validar que la paleta y tipografía estén buenas (es su área)
- **Ivan:** enviar cuestionarios al cliente, anotar respuestas, mover datos a `content/es.json`, push a GitHub
- **Erebus (yo):** mantener el sitio, deployar, investigar errores, responder dudas técnicas
- **Cliente:** responder cuestionarios, proveer datos y fotos

---

**Última revisión:** 2026-07-07
**Sitio:** 🟢 LIVE
**Status cueestionarios:** ⏳ 0/8 respondidos
**Próximo paso:** Ivan enviar Cuestionario 01 al cliente
