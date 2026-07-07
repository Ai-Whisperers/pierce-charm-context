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
