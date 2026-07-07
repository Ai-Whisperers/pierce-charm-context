# 📞 Notas cliente — Piercer (2026-07-07)

> Tomadas del audio largo de la reunión. **No todo entra al sitio todavía.**
> Ver `content/es.json → client_qa_notes` para lo que sí va.

---

## ✅ Lo que está confirmado y guardado en `client_qa_notes`

Lo demás del resto confirma lo que ya está implementado, pero lo guardo aquí en formato extendido:

### Datos del estudio (Cuestionario 01)
- Tipo: persona física, sin documentos aún → facturar como "Pierce Charm"
- Razón social: same as business name — pendiente
- Ubicacion planeada: vitrine commercial con showroom, 2+ ambientes (aún no tiene dirección)
- Wi-Fi, aire, baño cliente: sí
- Horarios: L-V 12-20, Sáb 9-15, Dom Cerrado, Feriados internacionales Cerrado
- Tiempo espera sin cita: 15 min libre / 30-45 min lleno

### Servicios y políticas
- Cambio de joya post-cicatrización: gratis si lo hicimos
- Downsizing: sí
- Retiro piercing problemático: sí
- Eventos privados: sí (ella va al evento como piercer)
- Sin cita para vender joyería: sí
- Combos/promos: 2x1, bundles
- Programa fidelidad (no referido): X visitas → descuento o piercing gratis
- Base de datos de clientes: sí (con CI + tracking)

### Joyería
- No diseñan propia; revenden
- Diseño por encargo: sí, a futuro
- Rango precios: Gs 50.000 - 125.000
- Materiales: titanio (ASTM F136) primera opción, acero quirúrgico
- Colores joyería: plateado, negro, dorado, tornasol, rojo/rosado

### Bioseguridad
- Autoclave: NO propia (se terceriza a clínica odontológica — no se muestra en web)
- Instrumental por cliente: sí
- Agujas: cateter + aguja americana. Piercing gun: PROHIBIDO
- Alergias: titanio hipoalergénico si no tolera acero
- Jóya inicial certificada y sellada

### Procedimiento de perforación
- Consulta previa: 10-15 min, con espejo para marcar
- Anestesia tópica: NO funciona, no se usa
- Anestesia local: en fase futura cuando certifique dosaje
- Nervous handling: 3 respiraciones + ojos cerrados
- Consentimiento informado firmado: siempre
- Foto post-perforación: sí (para redes)
- Seguimiento WhatsApp: 1 sem, 1 mes, 3 meses (cambio de joya)
- Bot WhatsApp para triage inicial

### Cuidados
- Solución fisiológica + jabón neutro
- NO alcohol, agua oxigenada, cremas con perfume, peróxido
- No dormir, no pileta, no manipular

### Edad
- Lóbulo: cualquier edad con padres
- Face: 14-15 años con CI adulta + CI menor
- Expansiones: 18+
- Verificación relación: comparación de apellido

### Piercer
- Luana López (es la propia piercer — confirmád que aparece en sitio como "Luana")
- Certificación actual: body piercing
- Trabaja sola. Mentor anterior pero no actual.

### Estética (a aplicar al sitio)
- **Colores MÁS vibrantes** — subir saturación, hue llamativo
- Símbolos: calavera, cruz invertida
- Luna vibrante roja (no está en el sitio actual)
- Decoraciones deben **variar por página** (no repetir siempre las mismas)
- Animaciones: murciélagos aleteando (3 frames), llamas parpadeando
- Estrellitas/lucitos en dorado o colores fríos
- Estilo "piercing-friendly", que no compita con tatuajes futuros

### Tono (a aplicar al sitio)
- 3 palabras: alternativo + profesional + friendly
- Tercera persona ("el estudio", "lo hacemos") + mezcla con formal/informal
- Vos sí, tú para formal
- Mínima jerga (puede usar el término inglés "downsize" pero en general español)
- LGBTQ+ friendly, antipatriarcal, ecológica, comunitaria

---

## 🟡 Lo que necesita confirmación ANTES de tocar

Estos cambios requieren que validemos con Luana/Ivan antes porque pueden chocar con implementaciones existentes:

### Cambios estructurales (no se aplican auto)
| # | Lo que pide el cliente | Conflicto potencial |
|---|---|---|
| E1 | **Home: botones de catálogo abajo**, no arriba (que se descubra scroleando) | La home actual tiene CTA arriba y abajo. **Cambiar:** subir los nav links en sí, bajar el CTA Reservar. Las cards del catálogo pueden aparecer después del hero, no antes. |
| E2 | **Sección "Donde el cuerpo se vuelve lienzo"** → agregar párrafo sobre historia/significado de los piercings (profundidad editorial) | Es una **sección nueva** que aún no existe. Hay que decidir si la creamos ahora o en segunda iteración. |
| E3 | **"Joyería curada" → "Joyería alternativa"** o "Joyería de primera calidad" | El nombre actual es "Joyería curada". Es un cambio chico de copy, no de estructura. |
| E4 | **Renombrar "sepultura y góticos" → "alternative style"** en la categoría de la galería | Cambio chico |
| E5 | **Rename "cap tips" → "expansores"** en categoría de la galería | Cambio chico |
| E6 | **Imagen de oreja: cada hover muestra foto real del piercing, no deshabilitar el menú "alternativo entre opciones"** en la lista, mostrar hover del nombre + foto en la oreja | Reescribir EarAnatomy. Recomendable: mejor solución = **hover highlight en la oreja**, no foto (que las fotos van en la sección post-lanzamiento). Pero si el cliente quiere, hacer highlight de **color** por piercing, no foto. |
| E7 | **Catálogo separado:** perforaciones / joyería — son 2 secciones separadas, no 1 sola | Hay que ver el diseño del catálogo — Piercings actual tiene 4 sub-tab (básico, cartílago, industrial, otros). **Decidir:** crear `/catalogo-joyeria` separado o agregar toggle. **Lo más simple: toggle.** |
| E8 | **Filtros joyería: material + color + zona + estilo** | El sitio actual no tiene filtros. **Esto es una sección nueva.** Puede ser MVP: 3 filtros básicos (material/color/zona). Listo para hacer cuando recibamos la compra inicial de stock. |
| E9 | **El botón "Reservar por WhatsApp" en tarjeta de piercing → "Solicitar presupuesto"** con mensaje pre-armado específico de la pieza | Cambiar copy y URL del wa.me con el nombre de la pieza. |
| E10 | **Menú debajo del navbar:** tipo ticker con "joyería nueva para vos" / "innová tu estilo" — keywords rotando | Esto es un banner pequeño encima de la línea de fondo entre header y home. **Sección nueva.** Se puede implementar con un array en es.json. |
| E11 | **Página "nosotros": cambiar "bioseguridad absoluta" (que ya está en home) → "principios"** que sean los valores de la marca (no repetir lo mismo) | Cambio chico, pero hay que reescribir el array de valores en es.json. |
| E12 | **Foto BEFORE/AFTER** en `/nosotros` para mostrar evidencia de procesos | Implementable, pero **requiere fotos del cliente** (que aún no tenemos). **Placeholder honesto "Pendiente foto real"** hasta que lleguen. |
| E13 | **En /nosotros: en lugar de estudio con SVG placeholders → "experiencias en el estudio", "resultados de piercings cobrados", "cómo se ven"** | Cambio de concepto + requiere fotos reales. **Fase post-lanzamiento.** |
| E14 | **Botón arriba en navbar:** botón fijo que dice "Conocer galería" o algo visible todo el tiempo | Decidir si ya está cubierto por "Reservar" o agregar uno nuevo. |
| E15 | **Slider donde el cliente arma su pedido: agregar items a "carrito invisible" + al final → WhatsApp con resumen** | Es una **feature nueva** tipo e-commerce lite. **No MVP** pero vale la pena planear. |
| E16 | **`/nosotros`: mostrar que son LGBTQ+ friendly, antipatriarcar, ecológico** | **Sí implementar** — agregar manifesto en la sección valores. |

### Cambios de UX (depende de lo que decidas)
| # | Lo que pide el cliente | Facilidad |
|---|---|---|
| U1 | Hover en la oreja → muestra nombre del piercing en lugar de selección por colores | Bajo esfuerzo |
| U2 | Quote/petición en el catálogo: agrega al "carrito" y al confirmar → manda al WhatsApp | Alto esfuerzo — e-commerce lite |
| U3 | En /contacto: el botón WhatsApp debe abrir directamente con mensaje auto | Bajo esfuerzo (1 click) |
| U4 | En /contacto: el WhatsApp actual es visible pero un poco hidden — revisar visibilidad | Bajo esfuerzo |

### Cambios de copy (automáticos, seguros)
| # | Cambio |
|---|---|
| C1 | "Joyería curada" → "Joyería alternativa" |
| C2 | Categoría gallery: "Sepultura y góticos" → "Alternative style" |
| C3 | Categoría gallery: "Cap tips" → "Expansores" |
| C4 | Card "Reservar por WhatsApp" → "Solicitar presupuesto" con mensaje pre-armado por pieza |
| C5 | Manteniendo estructura de `/nosotros`, refocar a valores (no a bioseguridad repetido) |
| C6 | Agregar manifiesto al final de `/nosotros` (LGBTQ+ friendly, antipatriarcar, ecológico, comunitario) |
| C7 | Tono general más cálido en el sitio (formal/informal mezcla, vos no tú) |
| C8 | Decorar la home con `<BannerTicker>` rotando mensajes alternativos (joyería nueva, innovación) |

---

## 🔴 Lo que tenemos que esperar al cliente

### Datos que el cliente va a confirmar después:
1. WhatsApp real del estudio
2. Email real (público + facturación)
3. Instagram @handle
4. TikTok @handle
5. Facebook URL de página
6. Dirección real (barrio + referencias)
7. Documentos de RUC / registro de nombre
8. Estudio físico aprobado y adjudicado

### Documentos pendientes:
- Razón social / RUC
- Cédula de autorización de uso de marca si la quiere Luana diseñada

### Inventario:
- Stock inicial de joyería (cuáles piezas, cuántos)
- Definir qué marcas de titanio certificada van a usar

### Logos:
- Logo formal diseñado por Luana (al día de hoy: solo wordmark + rombo con letra P)

---

## 📋 Decisión que NECESITAMOS tomar con Ivan/Luana HOY

### Preguntas a resolver esta tarde:
1. **E1 ¿Bajamos el CTA principal del home?** El cliente dijo "el catálogo un poco más abajo, descubrirlo scroleando" — lo aplicamos?
2. **E6 ¿Imagen hover con foto real vs highlight por color en el mapa de oreja?** Como no hay fotos, lo más sensato es **highlight por color**. Pero el cliente quiere foto real. ¿Hacemos highlight hoy y fotos reales post-lanzamiento?
3. **E7 ¿Catálogo separado perforaciones/joyería o toggle único?** El cliente pidió 2 secciones. **Toggle + /galeria** se puede implementar rápido (2-4h).
4. **E16 Manifesto en /nosotros** — sí, lo agregamos hoy (cambio de copy).
5. **E9 Botón "Reservar" → "Solicitar presupuesto"** con wa.me específico — sí, copy change.
6. **Dorado + vibrantes:** el cliente quiere colores más vibrantes. ¿Subimos saturación de #63081d o usamos un acento adicional más vibrante?

### Lo que NO se discute hoy, queda para después:
- E8 Filtros de joyería complejos (cuando llegue inventario)
- E15 Carrito invisible (e-commerce lite, MVP2)
- E12 Before/After y E13 experiencias (cuando lleguen fotos)
- E10 Ticker arriba del navbar (segunda iteración)

---

## 🎯 Lo que hago yo (Erebus) ahora

Voy a aplicar las cosas seguras hoy:

**Fase 1 (aplicar sin preguntar):** C2, C3, C4, C5, C6, C8 — son cambios de copy o texto
**Fase 2 (aplicar con OK implícito):** E1 (bajar CTA), E2 (crear sección editorial historia), E16 manifesto
**Fase 3 (preguntar antes):** E6 (mapa imagen vs hover), E7 (catálogo separado)

Si querés que aplique todas las fases 1+2+3, lo hago. Las decisiones que quedan son las **fase 4+** que requieren inventario o fotos del cliente.
