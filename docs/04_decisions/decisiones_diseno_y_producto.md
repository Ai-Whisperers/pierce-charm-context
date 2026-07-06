# Decisiones de diseño y producto

> Bitácora de decisiones tomadas durante el desarrollo del sitio. Cada decisión incluye el contexto y la razón.

## D1 — Modo oscuro único (sin switcher)

**Fecha:** 2026-07-06
**Contexto:** Los 3 HEX acordados (`#63081d`, `#211b54`, `#520b4e`) son oscuros. Toda la paleta pide fondo negro/gothic.
**Decisión:** El sitio es dark-mode único. No hay switcher a light mode.
**Razón:** Coherencia con la marca + paleta hardcodeada oscura. Un switcher requeriría definir paletas light que el cliente no pidió.

## D2 — Mapa interactivo de oreja con hotspots

**Fecha:** 2026-07-06
**Contexto:** El cliente pidió que los clientes puedan "elegir la perforación y presupuestar la cita".
**Decisión:** SVG custom de oreja con hotspots clickeables. Cada hotspot abre la card del piercing correspondiente y muestra precio.
**Implementación:**
- `components/EarAnatomy.tsx` — SVG oreja con paths simplificados
- Coordenadas `{x, y}` en % por cada piercing con posición
- Hotspots de 16px redondos con glow dorado
- Hover → tooltip con nombre + precio
- Click → scroll a la card completa del piercing en la lista
**Alternativas consideradas:**
- Foto real de oreja con hotspots → no tenemos fotos
- Ear diagram más detallado (con anatomía) → overkill, simplificado funciona

## D3 — Catálogo de piercings con niveles 1/2/3

**Fecha:** 2026-07-06
**Contexto:** Hay 19 tipos de perforaciones distintas. Mostrarlas todas como lista plana abruma.
**Decisión:** Agrupar por zona (Lóbulo / Cartílago / Industrial / Otros) + marcar nivel de cuidado (1 = fácil, 2 = medio, 3 = avanzado) con cruces invertidas.
**Razón:** El cliente quiere que los clientes "presupuesten" — necesitan entender de antemano que un rook (nivel 3) es más serio que un lóbulo (nivel 1).

## D4 — Estética dark/gothic coherente con la marca

**Fecha:** 2026-07-06
**Contexto:** El cliente pidió explícitamente decoraciones de cadenas, murciélagos, calaveras.
**Decisión:** Usar SVG inline (no imágenes) para todas las decoraciones. Animarlas con CSS keyframes (`batGlide`, `flicker`, `pulseGlow`).
**Razón:**
- SVG escala sin pixelarse
- Se colorean por CSS variables (cambiar paleta = cambiar todo)
- Animaciones CSS son gratuitas en performance

## D5 — Tipografía display Cinzel + Tangerine para acentos

**Fecha:** 2026-07-06
**Contexto:** Necesitamos una tipografía con peso visual que transmita la estética dark/gothic sin caer en fuentes cliché.
**Decisión:** Cinzel para display + Tangerine para acentos cursivos + Inter para body.
**Considerado y descartado:**
- Playfair Display → más serif clásica, menos gótica
- UnifrakturCook → demasiado alemán medieval, ilegible en mobile
- Cormorant Garamond → demasiado elegante, no encaja con la estética alternativa

## D6 — Niveles de cuidado con cruces invertidas

**Fecha:** 2026-07-06
**Decisión:** En vez de números o estrellas, usar cruces invertidas (✝️ invertida = gothic altar) para marcar niveles.
**Por qué:** Reusa un ornamento ya presente + visualmente coherente con la estética.

## D7 — WhatsApp como CTA principal en todas las páginas

**Fecha:** 2026-07-06
**Contexto:** El cliente maneja todas las consultas y reservas por WhatsApp.
**Decisión:**
- Botón "Reservar" en header siempre visible
- Botón flotante de WhatsApp en bottom-right de toda página (con glow animado)
- Botón principal de "Consultar por WhatsApp" en cada card de piercing
- Formato del mensaje pre-cargado por contexto (ej: "Hola! Quiero reservar la perforación: Tragus")

## D8 — No agregamos chat en vivo, blog, ni tienda online

**Fecha:** 2026-07-06
**Contexto:** Template tiene blog + tienda, podríamos haberlas dejado.
**Decisión:** Sitio mínimo viable sin blog ni tienda. Solo lo que el cliente pidió + navegación.
**Razón:** El cliente puede vender joyería físicamente; el sitio es para mostrar el catálogo, no para e-commerce.

## D9 — `experimental.globalNotFound: false` en next.config

**Fecha:** 2026-07-06
**Contexto:** Next.js 16 falla al prerenderizar el `/_global-error` con `useContext` error.
**Decisión:** Aplicar el mismo workaround que `dra-gabriela` ya tiene en producción.
**Razón:** Bug upstream de Next 16, no podemos hacer nada del lado del código del cliente.