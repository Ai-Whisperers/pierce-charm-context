# ⚡ QUICK START PARA LUANA

> Lo mínimo que necesitás saber para entender dónde está el proyecto.
> Leé primero `PACK_PARA_CLIENTE.md` si querés el detalle.

## 🌐 Sitio web del cliente

**LIVE en:** **https://piercecharm.paragu-ai.com/**

Estudio de piercings dark/gothic en Asunción, Paraguay. Hosting en subdominio estándar de Ai-Whisperers.

## 🔗 Los 2 repos

| Repo | Para qué | Link |
|---|---|---|
| **Sitio web** | El código del sitio (Next.js, components, content) | https://github.com/Ai-Whisperers/paragu-ai-platform/tree/main/apps/pierce-charm |
| **Contexto del cliente** | Brief, cuestionarios, decisiones, notas, idea backlog | https://github.com/Ai-Whisperers/pierce-charm-context |

## 📋 Cuestionarios para el cliente

**8 cuestionarios (~215 preguntas) en** `docs/08_questionnaires/` del context repo:

| # | Tema | Link |
|---|---|---|
| 01 | Datos básicos del estudio | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/01_datos_basicos_estudio.md |
| 02 | Catálogo de piercings | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/02_catalogo_piercings.md |
| 03 | Joyería y catálogo | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/03_joyeria_catalogo.md |
| 04 | Bioseguridad y procesos | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/04_bioseguridad_procesos.md |
| 05 | Estética, marca y tono | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/05_estetica_marca_y_tono.md |
| 06 | Clientes y operaciones | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/06_clientes_y_operaciones.md |
| 07 | Marketing, redes y competencia | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/07_marketing_redes_competencia.md |
| 08 | Fotos y assets | https://raw.githubusercontent.com/Ai-Whisperers/pierce-charm-context/main/docs/08_questionnaires/08_fotos_y_assets.md |

## ✅ Lo que el sitio YA tiene

- 11 rutas live, todas 200
- 36 perforaciones en catálogo (22 face/body agregados en roast round 1)
- Mapa interactivo de oreja con hotspots
- 12 piezas de joyería en galería (con badge "Foto pendiente")
- 8 preguntas FAQ con schema JSON-LD
- Política de privacidad + Términos y condiciones (Ley 6534 PY)
- Cookie banner con opt-in
- OG image 1200×630 + twitter card
- Favicons multi-tamaño + apple-touch-icon
- Skip-to-content + accesibilidad WCAG
- CI/CD con GitHub Actions → push = auto deploy

## ⏳ Lo que falta

- Datos reales del cliente (los 8 cuestionarios)
- Fotos reales del estudio, del piercer, de la joyería
- Logo formal (si querés diseñarlo como trabajo aparte)

## 📊 Stack resumido

- **Next.js 16** App Router + Tailwind v4 + TypeScript
- **Paleta:** `#63081d` (burgundy) `#211b54` (midnight indigo) `#520b4e` (royal purple) `#d4a843` (gold decorativo)
- **Fonts:** Cinzel (display) + Tangerine (script) + Inter (body)
- **Hosting:** Docker Swarm + Traefik + Cloudflare proxy en VPS Paraguay

## 🚀 Deploy

- Push a `main` del monorepo = auto-deploy en ~3 minutos
- Ivan/Erebus edita `apps/pierce-charm/content/es.json` con respuestas del cliente, push, listo

## 🔐 Privacidad del repo

Ambos repos son **privados** (Ai-Whisperers). No compartir enlaces directamente con el cliente — solo el sitio web público.
