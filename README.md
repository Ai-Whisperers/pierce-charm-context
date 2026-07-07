# Pierce Charm — Context Repository

> **Repo de contexto del cliente Pierce Charm.**
> Aquí vive la historia del proyecto: el brief original, reuniones, decisiones, investigación de marca, competidores, ideas sueltas, backlog de cambios.
>
> **El sitio web NO vive acá.** Vive en:
> **[`Ai-Whisperers/paragu-ai-platform/apps/pierce-charm`](https://github.com/Ai-Whisperers/paragu-ai-platform/tree/main/apps/pierce-charm)**
>
> Cualquier cambio de contenido del sitio (precios, copy, piercings, horarios) se hace editando `content/es.json` **allá**, no en este repo.

---

## Estructura

```
docs/
  01_brief/        — Brief original del cliente (lo que nos dieron al inicio)
  02_meetings/     — Notas de cada reunión (WhatsApp, llamada, presencial)
  03_research/     — Investigación de mercado, diseño, técnicas de piercing
  04_decisions/    — Decisiones de diseño/producto que se tomaron y por qué
  05_brand/        — Paleta, tipografía, mood board, assets de marca
  06_competitors/  — Otros estudios de piercing en Paraguay y LATAM
  07_backlog/      — Ideas sueltas, TODOs, cosas para próximas iteraciones

assets/
  logo/            — Archivos fuente del logo (SVG, PNG, AI)
  photos/          — Fotos del estudio y de piezas de joyería
  mood-board/      — Imágenes de referencia estética

content/           — Copy drafts que después se mueven al content/es.json del sitio
```

## Cliente

- **Nombre comercial:** Pierce Charm
- **Qué hace:** Estudio de piercings profesionales + venta de joyería alternativa
- **Dónde:** Asunción, Paraguay (dirección exacta solo por WhatsApp al confirmar cita)
- **Estética:** Política alternativa · dark/gothic · cadenas, calaveras, murciélagos, cruces invertidas
- **Público objetivo:** Personas que buscan piercing profesional con identidad política y estética dark
- **Paleta acordada:**
  - `#63081d` burgundy / sangre — primary
  - `#211b54` midnight indigo — secondary
  - `#520b4e` royal purple — accent
  - `#b08838` dorado — decoración

## Stack del sitio

- **Repo:** `Ai-Whisperers/paragu-ai-platform` (monorepo Next.js)
- **App path:** `apps/pierce-charm`
- **Next.js 16** + Tailwind v4 + TypeScript
- **Contenido:** 100% en `content/es.json` (sin literales hardcodeados en JSX)

## Cómo se actualiza el sitio

1. Cambios de contenido → editar `apps/pierce-charm/content/es.json` en el repo del monorepo
2. Cambios de paleta/CSS → editar `apps/pierce-charm/app/globals.css` y `content/tokens.json`
3. Cambios estructurales (rutas, componentes) → crear PR con review
4. Deploy se dispara automático en push a `main` del monorepo

## Contacto del cliente

- **WhatsApp:** +595 981 324 569
- **Instagram:** @pierce.charm
- **Email:** hola@piercecharm.com.py (pendiente confirmar)

---

_Maintenido por Ai-Whisperers · Última actualización: ver git log_

## Estado al 2026-07-07 (Roast Round 1)

Completé la primera ronda de upgrades sobre el sitio. Items resueltos:

**HOY (4 fixes)**
- [x] Phone ahora viene de `content/es.json` (no más hardcode en JSX)
- [x] `/sitemap.xml` retorna 200 (antes era 404)
- [x] OG image 1200×630 PNG + twitter card meta
- [x] FAQ: JSON-LD FAQPage schema para Google rich snippets

**ESTA SEMANA (5 fixes)**
- [x] Catálogo: 18 → 36 piercings (22 nuevos body/face agregados)
- [x] Galería: badge honesto "Foto pendiente" (no más SVG variants repetidos)
- [x] Nosotros: mismo badge en placeholders del estudio
- [x] Favicon: 8 tamaños + apple-touch-icon
- [x] Skip-to-content + aria-expanded + aria-current

**LANZAMIENTO**
- [x] /privacidad (Ley 6534 PY + derechos ARCO)
- [x] /terminos (depósito, cuidados, menores, devoluciones)
- [x] Cookie banner con localStorage opt-in
- [x] WCAG: gold #b08838→#d4a843, primary-light #8b1a31→#b2364f
- [x] /piercings?pin=<id>: persist + auto-scroll
- [x] GitHub Actions CI/CD para build+deploy
- [x] Sin literales hardcoded en JSX (todo via lib/site-config.ts helper)

**Pendiente (cliente debe proveer)**
- [ ] WhatsApp real del estudio (Cuestionario 01)
- [ ] Instagram handle real
- [ ] Email real
- [ ] Dirección + barrio + referencias
- [ ] Horarios reales
- [ ] Foto del estudio, del piercer, de las piezas de joyería
- [ ] Logo formal (Luana López puede diseñarlo)

Deploy: https://piercecharm.paragu-ai.com/
