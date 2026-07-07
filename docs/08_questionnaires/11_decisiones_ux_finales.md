# Cuestionario 11 — Decisiones UX pendientes

> **Owner:** Ivan/Luana — confirman o rechazan cada punto antes de implementar.
> **Status:** Documentado en `docs/HANDOFF/CLIENTE_RESPUESTAS_2026-07-07.md` (code E1-E16).
> Cuando termine esta fase, este cuestionario se archiva.

---

## E1. ¿Bajamos el CTA "Reservar por WhatsApp" del home?

Hoy está arriba (visible sin scrollear) y abajo del catálogo teaser.

- [ ] **Sí** — que el cliente descubra scroleando el catálogo, después aparece WhatsApp.
- [ ] **No** — mantener el CTA arriba para conversión directa.
- [ ] **Mix** — CTA arriba pequeño + CTA secundario al final.

## E2. Crear sección editorial "Donde el cuerpo se vuelve lienzo"

Cliente pidió agregar párrafo sobre historia/significado de los piercings.

- [ ] **Sí**, crear sección con copy de ~3 párrafos.
- [ ] **Sí**, pero más corto (1 párrafo + título).
- [ ] **No por ahora** — dejar para segunda iteración.

## E6. Mapa interactivo de oreja: hover muestra qué?

Hoy hay 14 pins en el mapa. Cliente pidió ver "hover con foto real, no alternativas que saturan".

- [ ] **Sin fotos aún** → highlight por color al hacer hover.
- [ ] **Sin fotos aún** → tooltip con nombre del piercing + descripción.
- [ ] **Cuando tengamos fotos** → foto real del piercing al hacer hover.

## E7. Catálogo: ¿perforaciones y joyería en una sola sección o separadas?

Cliente pidió "catálogo separado perforaciones/joyería".

- [ ] **Separadas** — `/piercings` + `/joyeria`, cada una con su catálogo.
- [ ] **Toggle** — `/galeria` con tabs "Perforaciones | Joyería".
- [ ] **Combinada** — `/catalogo` con todo mezclado por categoría.

## E9. Botón CTA del catálogo: ¿qué dice?

Cliente pidió "Solicitar presupuesto" en lugar de "Reservar por WhatsApp".

- [ ] **"Solicitar presupuesto"** — formal + específico a la pieza.
- [ ] **"Reservar cita"** — más directo.
- [ ] **"Lo quiero"** — más emocional / alternativo.
- [ ] **"Preguntame por WhatsApp"** — más conversacional.

## E10. Banner ticker (deco arriba)

Cliente pidió "joyería nueva para vos / innová tu estilo".

- [ ] **Sí** — 4 mensajes rotando cada 5s.
- [ ] **Sí** — pero solo en home, no en otras páginas.
- [ ] **No** — quitar, distrae.

## E12. Before/After en /nosotros

Cliente pidió fotos antes/después como evidencia.

- [ ] **Sí** — carrusel con fotos reales (cuando lleguen).
- [ ] **Sí** — placeholder "Pendiente" hasta tener fotos.
- [ ] **No** — innecesario.

## E13. /nosotros: mostrar experiencias o sólo estudio?

- [ ] **Experiencias** — fotos de personas con piercings hechos.
- [ ] **Estudio** — fotos del local (cuando exista).
- [ ] **Ambas** — split half/half.

## E14. CTA fijo en navbar

Cliente pidió "Conocer galería" o equivalente visible todo el tiempo.

- [ ] **Sí** — botón adicional.
- [ ] **No** — el "Reservar" actual es suficiente.

## E15. Carrito invisible → WhatsApp summary

Cliente pidió "agregar items a un carrito invisible y mandar al WhatsApp con resumen".

- [ ] **Sí, MVP2** — feature de e-commerce lite (1-2 semanas).
- [ ] **No** — solo reservado por WhatsApp pieza a pieza.
- [ ] **Versión simple** — solo selección múltiple en /galeria → summary al WhatsApp.

## C1-C8. Copy fixes (todos ya aplicados)

Todos los "Cambios de copy" del round 1 fueron aplicados en el sitio. Ver `docs/HANDOFF/ROUND_2_APPLIED.md`.

## E16. Manifesto en /nosotros (ya aplicado)

- ✅ Manifiesto + principles + visión 3 años visibles en /nosotros.

---

## Próximos pasos

Para cada punto, Ivan/Luana marcan la preferencia. Erebus implementa lo aprobado en 1-2 días.


---

# Respuestas — Cuestionario 11 ✅ 2026-07-07 (audio 2)

## E1. ¿Bajamos el CTA "Reservar por WhatsApp" del home?
**✅ CONFIRMADO POR CLIENTE:**
- **Sacar del home el CTA gigante "Reservar por WhatsApp".**
- **Dejar UN solo CTA al FINAL de la página** (no repetir 20 veces lo mismo).
- El botón "Reservar" pequeño del navbar (top) **también se queda**, pero el footer-final es el principal.
- El botón de contacto va en `/contacto` (como está ahora).
- **Razón:** "no saturarle al cliente con el mismo mensaje una y otra vez".
- Mensaje implícito: el cliente no quiere agresividad comercial. Prefiere un cliente que explore, descubra, y reserve cuando decida.

## E2. Crear sección editorial "Donde el cuerpo se vuelve lienzo"
**✅ APLICADO DESPUÉS:** Cliente agregó que va a escribir ella misma el copy de esa sección.
- **Acción:** Erebus crea el contenedor/estructura con placeholder, Luana lo escribe (ella es artista + escribirá con su voz personal).

## E3-E5 (cambios de copy)
**✅ YA APLICADO en rondas previas** —"Joyería alternativa", "Alternative style", "Expansores".

## E6. Mapa interactivo de oreja: hover muestra qué?
**✅ CONFIRMADO POR CLIENTE:**
- **Foto real de oreja 4K HD con piercings hechos** (no abstract anchors amarillos).
- Al hover, **TODO el piercing se resalta + agranda** (highlight full-size, no solo outline).
- **Cada piercing es la unidad visual completa**, no solo un punto.
- Erebus genera la oreja en HD detailed realistic + zoom/highlight on hover.
- **Acción:** cuando se implemente, generar /public/ear-highres.jpg + mapear highlights por piercing.

## E7. Catálogo: ¿separar perforaciones/joyería o toggle?
**✅ CLIENTE PIDIÓ AMBAS SEPARADAS.**
- `/piercings` (perforaciones) ← actual con tabs por categoría
- `/galeria` (joyería) ← actual
- **Toggle "Lo quiero" / "Solicitar presupuesto" en el catálogo de joyería**: si seleccionado, item se agrega al carrito invisible.

## E8. Filtros de joyería (material + color + zona)
**⏳ POSTPAGADO** — activar cuando llegue el inventario del Cuestionario 09.

## E9. Botón CTA del catálogo: ¿qué dice?
**✅ CONFIRMADO POR CLIENTE (mix):**
- En /piercings, debajo del catálogo: **barra fija "Reservar cita"** que aparece cuando el cliente ya tiene items en el carrito invisible.
- El catálogo permite "Agregar" → click → llena info necesaria → CTA final al WhatsApp.
- Botón por defecto: **"Lo quiero"** (alternativo + emocional) en cada card de joyería de /galeria.
- Botón final del carrito: **"Reservar cita"** (claro).

## E10. Banner ticker deco
**✅ CONFIRMADO POR CLIENTE:**
- **DEBAJO del navbar**, no arriba.
- Sigue al navbar mientras scrolleas (sticky).
- Mensajes rotando cada 5-8 seg.
- No tapa las tabs.

## E11. /nosotros: principios vs bioseguridad repetida
**✅ YA APLICADO** en round 1+3 — manifesto + principles + piercer + vision_3_anios.

## E12. Before/After en /nosotros
**✅ CONFIRMADO POR CLIENTE:** SÍ, pero **DESPUÉS** (cuando haya fotos reales de su trabajo).

## E13. /nosotros: mostrar experiencias o sólo estudio?
**✅ CONFIRMADO POR CLIENTE:**
- Foco en **visión del estudio + por qué hacemos piercings + compromiso con el cliente**.
- No solo "el estudio" ni solo "experiencias".
- Mencionar a la piercer Luana (es performer/artista con cantantes) en /nosotros.
- Luana es artista + colaboradora con cantantes/performers — esto la hace diferente.

## E14. CTA fijo en navbar
**✅ CONFIRMADO POR CLIENTE:**
- **No es tan necesario** — se queda el de "Reservar" actual (botón pequeño + WhatsApp Float).
- "Three times is not too much around the page" — no agregar más.

## E15. Carrito invisible → WhatsApp summary
**✅ CONFIRMADO — feature nueva, MVP2:**
- **Carrito invisible MIENTRAS la sesión** del cliente (no se guarda tras cerrar el navegador por ahora).
- Contiene: **joyas + agujeros por zona + costo sesión (fee 50-100K) + tiempo total estimado de la perforación**.
- Cuando confirma:
  - Se abre WhatsApp con resumen.
  - Pasa por un **consentimiento online (Google Form corto)** primero.
  - Después → bot IA triage.
  - Cuando el bot termine las preguntas de seguridad + datos del cliente → pasa al **WhatsApp REAL de Luana** (handoff humano).

### MVP2 stack
- Cliente persiste items en `sessionStorage` (no localStorage, para limpiar al cerrar navegador).
- Resumen al confirmar → WhatsApp con wa.me pre-armado + payload visible para Luana.
- Google Form: tipo `https://forms.gle/xxxxx` con campos: nombre, CI, edad, zona, alergias, firma digital.
- Bot: Evolution API + Hermes agent existente (Luana puede pedirle a Erebus).

## E16. Manifesto en /nosotros
**✅ YA APLICADO** — manifesto "Más que un estudio" con 4 valores: LGBTQ+, antipatriarcal, sustentabilidad, comunidad.

## C1-C8 ✅ Cambios de copy ya aplicados.

## U1-U4 ✅ UX improvements menores ya aplicados.

## Resumen ejecutivo de las decisiones del audio 2

| Código | Decisión | Status |
|---|---|---|
| E1 | UN CTA en home, al final | ✅ Aplicar |
| E2 | "Donde el cuerpo se vuelve lienzo" → Luana escribe | ✅ Estructura creada |
| E6 | Oreja 4K HD en /piercings con piercings reales | ⏳ Requiere assets |
| E7 | Toggle perforaciones/joyería | ✅ Ya separados |
| E9 | "Lo quiero" / "Solicitar presupuesto" / "Reservar cita" mix | ✅ Aplicar |
| E10 | Banner ticker sticky debajo del navbar | ⏳ Aplicar |
| E12 | Before/After después | ⏳ Trigger: fotos |
| E13 | /nosotros = visión + performer + compromiso | ✅ Aplicar |
| E14 | Sin CTA adicional | ✅ Confirmar |
| E15 | Carrito MVP2 | ⏳ Trigger: post-lanzamiento |
| E16 | Manifesto | ✅ Aplicado |