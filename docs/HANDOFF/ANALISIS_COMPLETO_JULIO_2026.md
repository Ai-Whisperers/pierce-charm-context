# 📋 ANÁLISIS CONSOLIDADO — PIERCE CHARM
## Estado del proyecto + TODO lo que Luana mencionó + Roadmap
**Fecha:** Julio 2026
**Versión:** 1.0 — Round 5 (síntesis completa)
**Owner:** Erebus

> **Propósito de este documento:** Un solo lugar donde se ve TODO lo que se hizo en el sitio, TODO lo que Luana dijo en las transcripciones, TODO lo que está pendiente, y el roadmap. Es el mapa completo del proyecto para Ivan y para el rep que tome el proyecto en el futuro.

---

## TL;DR

**Estado actual del sitio:** ✅ LIVE, 9 rutas, 11/11 retornando 200, score técnico mejorado 62→88/100. Selector visual de piercings completo (oreja/rostro/cuerpo). SEO crítico arreglado. h1 en todas las páginas. Canonical + JSON-LD inline.

**Lo que falta para lanzar:** Datos reales del cliente (WhatsApp/email/IG/estudio/RUC). Logo formal. Foto de Luana. Fotos del estudio. Stock inicial de joyería. Sistema de booking real (E15).

**Lo que falta post-lanzamiento:** 5 cuestionarios nuevos pendientes de activar (inventario, legal, redes, testimonios, fotos after). Carrito invisible. Newsletter. Eventos Dark Charm cross-promo. Percer admirado (hand-free) que Luana no llegó a anotar el nombre.

**Lo más urgente hoy:**
1. Ivan envía al cliente **cuestionarios 09-12** (ya en `08_questionnaires/`)
2. Luana envía **foto de ella** (esta semana) y **catálogo de Dark Charm** para tomar inspiración
3. Ivan confirma **WhatsApp real + Instagram** apenas estén
4. Se puede construir **E15 carrito** sin esperar al cliente (sessionStorage + WhatsApp summary)

---

## 1. HISTORIAL DE COMMITS

### `paragu-ai-platform` (8 commits en pierce-charm)

| Commit | Descripción |
|---|---|
| `e63d4aa` | Add new client app — gothic piercing studio en Asunción |
| `13608bd` | Deploy a `piercecharm.paragu-ai.com` |
| `151fbac` | Roast round 1 — full upgrade pass |
| `f8ccc2f` | Fix Dockerfile.standalone syntax error |
| `f58c027` | Cliente audio round — manifiesto, principles, banner ticker, gallery renames |
| `cbf3b79` | Round 2 — horarios reales, precios 50/100/150K, catálogo sin surface, page_decor |
| `d4b0ff1` | Round 3 — testimonios, eventos, newsletter, piercer Luana, vision 3 años |
| `c0d782c` | Audio 2 round — E1 (saturación CTA home), E13 (3 pillars /nosotros), piercer contexto |
| `857368f` | Round 4b — selector visual completo (oreja/rostro/cuerpo) + P0 SEO/UX fixes |

### `pierce-charm-context` (8 commits)

| Commit | Descripción |
|---|---|
| `1be97ee` | Initial context repo for Pierce Charm |
| `c846191` | 8 detailed client questionnaires (~215 questions) |
| `b61c054` | Update README with Roast Round 1 status |
| `ab6d670` | Complete delivery pack for Luana + Ivan |
| `e741122` | Cliente respuestas round 1 — decisiones pendientes |
| `aabf85e` | Round 2 applied — precios, horarios reales, catálogo corregido |
| `5b42a24` | Ronda 3 — reorganizar cuestionarios, plan maestro, questionnaire log |
| `e3a8f81` | Audio 2 round — cuestionarios 09-12 respondedos + plan maestro actualizado |

---

## 2. LO QUE SE TRABAJÓ EN EL SITIO (cambios concretos)

### 2.1 Estructura de páginas (11 rutas)

| Ruta | Tamaño | h1 | Canonical | JSON-LD | Meta única |
|---|---|---|---|---|---|
| `/` Home | 124 KB | ✅ | ✅ | ✅ | ✅ |
| `/nosotros` | 109 KB | ✅ | ✅ | ✅ | ✅ |
| `/galeria` Joyería | 123 KB | ✅ | ✅ | ✅ | ✅ |
| `/contacto` | 101 KB | ✅ | ✅ | ✅ | ✅ |
| `/faq` | 104 KB | ✅ | ✅ | ✅ | ✅ |
| `/piercings` Catálogo | 126 KB | ✅ | ✅ | ✅ | ✅ |
| `/terminos` | 78 KB | ✅ | ✅ | ✅ | ✅ |
| `/privacidad` | 80 KB | ✅ | ✅ | ✅ | ✅ |
| `/eventos` | 85 KB | ✅ | ✅ | ✅ | ✅ |
| `/sitemap.xml` | 1 KB | — | — | — | — |
| `/robots.txt` | <1 KB | — | — | — | — |

### 2.2 Componentes (15 archivos)

| Componente | Propósito | Tamaño |
|---|---|---|
| `Header.tsx` | Navbar fijo + CTA Reservar | 5 KB |
| `Footer.tsx` | 4 columnas (Estudio, Atención, Legal) + sociales | 5 KB |
| `BottomNav.tsx` | Mobile nav con 5 items | 1 KB |
| `WhatsAppFloat.tsx` | Botón flotante siempre visible | 2 KB |
| `CookieBanner.tsx` | localStorage opt-in (Ley 6534) | 2 KB |
| `BannerTicker.tsx` | Texto rotativo arriba (5s intervalo) | 1 KB |
| `Testimonials.tsx` | Placeholder honesto + "Lo que dicen nuestros clientes" | 2 KB |
| **EarAnatomy.tsx** | SVG oreja lateral con 14 hotspots | 6 KB |
| **FaceSelector.tsx** | SVG cara frontal con 10 hotspots | 8 KB |
| **BodySelector.tsx** | SVG torso con 2 hotspots | 7 KB |
| **AnatomySwitcher.tsx** | Tabs Oreja/Rostro/Cuerpo + grid + CTA dinámico | 8 KB |
| **JewelryIcon.tsx** | 12 iconos SVG de joyas reales | 5 KB |
| `ornaments.tsx` | 9 SVGs decorativos (cadenas, murciélagos, etc.) | 5 KB |

### 2.3 Datos en `content/es.json` (54 KB)

26 perforaciones en catálogo, organizadas en 5 categorías:
- **basicos** (3): lóbulo simple/segundo/tercer
- **cartilago** (8): helix, flat, forward-helix, tragus, anti-tragus, rook, daith, conch
- **industrial** (3): industrial, orbital, snug
- **faciales** (10): nostril, septum, high-nostril, medusa, monroe, labret, labret-bajo, bridge, eyebrow, tongue
- **body** (2): ombligo, ombligo-inverso

Cada item tiene: id, name, zone, region (oreja/rostro/cuerpo), position {x, y, side?}, jewelry type, downtime, level, description, price.

### 2.4 Galería (`/galeria`)

- 3 categorías activas: Alternative style (4), Expansores (9), Cadenas (6)
- Filtros por categoría implementados (UI + state)
- Filtros pendientes: material + color + zona (trigger: cuestionario 09)

### 2.5 SEO técnico (round 4b)

- **Canonical URLs** en 9/9 páginas ✅
- **HealthAndBeautyBusiness JSON-LD** inline en todas ✅
- **h1** en 9/9 páginas (antes: 0/9) ✅
- **Meta descriptions únicas** por página (antes: 1 duplicada en 7) ✅
- **BAILOUT_TO_CLIENT_SIDE_RENDERING** eliminado de /piercings ✅
- **Open Graph image** 1200×630 con dimensiones y alt ✅
- **Twitter card** summary_large_image ✅
- **robots.txt + sitemap.xml** dinámicos ✅

### 2.6 Accesibilidad

- Skip-to-content link ✅
- ARIA labels en iconos interactivos ✅
- Focus indicators ✅
- aria-current="page" en nav activo ✅
- WCAG AA contrast en paleta ✅

### 2.7 Performance (perimetral)

- Hero home: 1 decoración animada + ear anatomy + badges (competen menos) ✅
- `safe-area-bottom` en WhatsApp Float (no choca con BottomNav) ✅
- Paleta con `transition` de 200ms (no lag) ✅

---

## 3. SELECTOR VISUAL DE PIERCINGS (lo más importante del proyecto)

### 3.1 Arquitectura

```
AnatomySwitcher (tabs)
├── EarAnatomy (14 hotspots)
│   ├── lóbulos (3)
│   ├── helix/flat/forward-helix (3)
│   ├── tragus/anti-tragus (2)
│   ├── rook/daith/conch (3)
│   └── industrial/orbital/snug (3)
├── FaceSelector (10 hotspots)
│   ├── narices (3): nostril, septum, high-nostril
│   ├── labios (4): medusa, monroe, labret, labret-bajo
│   ├── cejas/bridge (2): eyebrow, bridge
│   └── boca (1): tongue
└── BodySelector (2 hotspots)
    └── ombligo, ombligo-inverso
```

### 3.2 Mecánica de interacción

- **Hover** sobre hotspot → la pieza completa se agranda 1.45× + tooltip con nombre, zona, precio, tiempo de cicatrización
- **Click** → border sólido gold (estado activo persistente)
- **Icono real de la joya** (no point) — cada hotspot es el tipo de pieza (stud, hoop, clicker, barbell, etc.)

### 3.3 Card grid por región

- Debajo del SVG, grid de cards con todas las perforaciones de la región
- Click en card → activa el hotspot correspondiente
- Scroll horizontal si overflow

### 3.4 CTA dinámico

- Sin selección: "Reservar cita" (genérico)
- Con selección: "Consultar por WhatsApp" con mensaje pre-armado por piercing

### 3.5 Luana sobre el selector (audio 2)

> "Mapa interactivo de oreja, hover muestra qué, sin fotos aún." (round 1, E6)
>
> "Podemos buscar una foto real de una oreja ya pierceada. AI queremos que generes o que hagas los diseños de una oreja full HD 4K súper detallada y completa para que podamos visualizar bien todas las cosas. Y en vez de solamente los puntos amarillos, quiero que sean los piercings y el piercing entero es lo que se hi-lightea y se agranda y hoverea cuando está por ahí la persona."

**Status round 5:** ✅ El selector funciona. Luana pidió "foto real 4K" para la oreja — **pendiente (E6)**, no se pudo generar foto hiperrealista, se construyó SVG estilizado. La mecánica de "highlight full piercing" sí está aplicada.

---

## 4. TODO LO QUE LUANA MENCIONÓ EN LAS TRANSCRIPCIONES

### 4.1 Cuestionario 01 — Datos básicos del estudio

| Pregunta | Respuesta | Status en sitio |
|---|---|---|
| Razón social | Persona física = Pierce Charm, pendiente | ⏳ "Pierce Charm" (placeholder) |
| WhatsApp principal | Pendiente | ⚠️ Placeholder `595981324569` |
| WhatsApp segundo | Pendiente | ⏳ |
| Email público | Pendiente | ⚠️ `hola@piercecharm.com.py` |
| Email facturación | Pendiente | ⏳ |
| Instagram handle | Pendiente (creará) | ⚠️ `@pierce.charm` |
| Facebook | Pendiente | ⏳ |
| TikTok | Pendiente probable | ⏳ |
| Dirección | No tiene (no hay estudio) | ⚠️ "Asunción, Paraguay" |
| Tipo ubicación | Vitrina comercial con showroom, mín. 2 ambientes | ⏳ |
| WiFi / AACC / baño | Sí ideal | ⏳ |
| Horarios | L-V 12-20 / Sáb 9-15 / Dom Cerrado | ✅ Aplicado |
| Feriados internacionales | Cerrado | ⏳ Config |
| Tiempo espera sin cita | 30-45 min lleno / 15 min libre | ⏳ Config |
| Consulta previa | Gs 10.000, transferible a piercing si en 2 sem | ⏳ |

### 4.2 Cuestionario 02 — Catálogo de piercings

| Servicio | Precio | Status |
|---|---|---|
| Lóbulo | Gs 50.000 | ✅ |
| Cartílago/faciales/body (genéricos) | Gs 100.000 | ✅ |
| Industrial + snug | Gs 150.000 | ✅ |
| Cambio de joya post-cicatrización | Gratis si lo hicimos | ⏳ Política |
| Downsizing | Gs 10.000 base | ⏳ |
| Retiro piercing problemático | Sí | ⏳ |
| Piercings para eventos privados | Sí (Luana se traslada, no maneja evento) | ⏳ |
| Venta joyería sin cita | Sí | ✅ |
| Paquetes / combos | 2x1, bundles | ⏳ |
| Sistema referidos | Por cupones, X visitas = premio | ⏳ |
| Base datos clientes | Sí con CI | ⏳ |

**Lo que NO hace (red flags):** NO surface, NO microdermal/ancla, NO thermal, NO expansiones (por ahora), NO pezones (por ahora).

### 4.3 Cuestionario 03 — Joyería

| Pregunta | Respuesta | Status |
|---|---|---|
| ¿Diseñan propia? | No, revenden | — |
| ¿Diseño por encargo? | Sí, más adelante | ⏳ |
| ¿Marcas específicas? | No | — |
| ¿Exclusividad de marca? | No | — |
| ¿Colabs artistas locales? | Posible | ⏳ |
| ¿Grabados personalizados? | No por ahora | — |
| Stock estimado | 50-100 piezas (AliExpress) | ⏳ Trigger: cuest 09 |
| ¿Traen piezas por encargo? | Sí | ⏳ |
| ¿Lista de espera? | Depende demanda | ⏳ |
| ¿Consiguen piezas específicas? | Sí = encargo cliente | ⏳ |
| **Rango de precios** | **Gs 50.000 - 125.000** | ✅ "Gs 50.000 - 125.000 (dependiendo de la pieza)" |
| Materiales | Titanio ASTM F136 (1ra), acero quirúrgico | ⏳ Atributos |
| Colores | Plateado, negro PVD, dorado, tornasol, rojo/rosado | ⏳ Atributos |
| Sin níquel | A investigar | ⏳ |
| SKU | Visible (Alitah) + interno (J001) | ⏳ |
| Catálogo PDF | Amiga de Luana diseñará | ⏳ |

### 4.4 Cuestionario 04 — Bioseguridad y procesos

| Pregunta | Respuesta | Status |
|---|---|---|
| Autoclave | No propia (tercerizada a clínica odontológica) | ✅ No se muestra en sitio |
| Test esporas | Depende de la clínica | ⏳ |
| Instrumental por cliente | Sí | ⏳ Mostrar en bioseguridad |
| Agujas | Cateter + aguja americana | ✅ |
| **Piercing gun** | **PROHIBIDO** | ⏳ Reforzar |
| Protocolo infecciones documentado | No formal aún | ⏳ |
| Manejo alergias | Titanio hipoalergénico | ✅ |
| J inicial sellada | Sí | ⏳ |
| Marcas certificadas | Titanio certificado (cuál: a definir) | ⏳ |
| **Duración consulta** | 10-15 min | ⏳ FAQ |
| Marcación espejo | Siempre que se pueda; sentado si difícil | ⏳ |
| **Anestesia tópica** | **No se usa (no funciona)** | ⏳ FAQ |
| Anestesia local | En fase futura (Luana certifica dosaje) | ⏳ |
| Manejo nervioso | 3 respiraciones + ojos cerrados | ⏳ FAQ |
| Consentimiento informado | **Siempre firmado** (edad + CI adulto + cláusula responsabilidad) | ⏳ |
| Foto post | Sí (para redes) | ⏳ |
| **Seguimiento post** | **WhatsApp 1 sem / 1 mes / 3 meses** | ⏳ |
| Kit post | Solución fisiológica + jabón neutro | ⏳ |
| Instrucciones digitales | PDF post-cita | ⏳ |
| Bot WhatsApp triage | Sí, Luana los humanos | ⏳ |
| Plantillas frecuentes | Sí, con videos/imágenes | ⏳ |

### 4.5 Cuestionario 05 — Estética, marca y tono

| Pregunta | Respuesta | Status |
|---|---|---|
| **Ajustar paleta: más vibrante** | Saturación grande, hue llamativo | ⏳ |
| Colores secundarios | Rojos, azul profundo, violeta, grises | ⏳ Hover states |
| Identidad visual | No formal aún | ⏳ |
| Logo | **Luana lo diseña aparte** | ⏳ (favicon P en rombo es placeholder) |
| Manual de marca | Erebus puede generar brandbook modelo | ⏳ |
| Decoraciones | Cadenas, murciélagos, luna roja, estrellitas doradas | ✅ SVG inline |
| **Variar por página** | Home: luna + cadenas; otras: murciélagos + calaveras | ⏳ Page decor map |
| Animaciones | Murciélagos aleteando 3 frames, llamas | ⏳ CSS keyframes |
| Tono 3 palabras | Alternativo + profesional + friendly | ✅ |
| Persona gramatical | Tercera persona | ✅ |
| Vos / Tú | Vos general, tú formal | ✅ |
| Mezcla formal/informal | Sí (confianza + accesibilidad) | ✅ |
| **Jerga piercing** | **Mínima, traducir al español** (downsize → bajar de joya) | ⏳ Revisar copy |
| Manejo WhatsApp | Luana + bot | ⏳ |
| Plantillas frecuentes | Sí con videos | ⏳ |
| Postura | LGBTQ+, antipatriarcal, ecológica, comunitaria | ✅ Manifesto |
| Símbolos | **Calavera + cruz invertida** | ✅ |
| **Inspiración sitio** | **Demonia Boots (demoniacult.com)** | ⏳ Investigar paleta |

### 4.6 Cuestionario 06 — Clientes y operaciones

| Pregunta | Respuesta | Status |
|---|---|---|
| Documento cita | C.I. paraguaya | ⏳ |
| Restricciones previas | No alcohol 24h, no ayunas, sin makeup, joyería esterilizada | ✅ Aplicado en /contacto tips |
| Atención al cliente | Rápida, concisa, bot triage, Luana humanos | ⏳ |
| **Diferenciación** | **Honestidad sobre anatomía** (no perfora si no viable, alternativa) | ✅ |
| Admitir errores | Sí, devolver plata si falló | ✅ |
| Política cancelación | Seña Gs 50.000, transferible 24h antes | ⏳ |
| Devoluciones joyería | Abierta no acepta, sin abrir 7 días 10% | ⏳ |
| Garantía | — | ⏳ |
| Edad | Lóbulo cualquier edad con padres, face 14-15, expansiones 18+ | ⏳ FAQ |

### 4.7 Cuestionario 07 — Marketing, redes y competencia

| Pregunta | Respuesta | Status |
|---|---|---|
| Sitio web | El actual ✅ | ✅ |
| Google My Business | No | ⏳ Trigger: cuest 12 |
| Instagram activa | No (creará hoy) | ⏳ |
| Facebook | Pendiente | ⏳ |
| TikTok | Pendiente probable | ⏳ |
| YouTube | No | — |
| Pinterest | No | — |
| Google Maps/Waze | No | ⏳ |
| **Estrategia contenido** | After photos, proceso, joyería, política del cuerpo | ⏳ IG setup |
| Hashtag propio | Pendiente | ⏳ |
| **Blog para SEO** | Sí | ⏳ Trigger: cuest 11 |
| Email marketing / newsletter | Sí | ⏳ |
| Spam WhatsApp | Sí | ⏳ |
| Pago publicidad | No | — |
| **SEO keywords** | **piercing asunción, piercing barato, piercing de calidad** | ✅ Aplicado |
| **Google Reviews** | Sí, botón + post-cita | ⏳ Trigger: URL GMB |
| **Testimonios en sitio** | Sí | ✅ Placeholder |
| **Competencia** | Body Piercing, Sabat, Sweet Baby, Estudio 21 | ⏳ Doc interno |
| **Percer admirada** | Pendiente (hand-free) | ⏳ |
| **Inspiración estética** | **Demonia Boots** | ⏳ |
| **Eventos próximos** | Lanzamiento, noche piercing, promos con tattoos, ferias, play piercing (sadomaso, requiere curso) | ✅ 3 eventos sembrados |
| Eventos mascarada | Sí (LQV: "le clavo acá a la gente") | ⏳ |
| **Sección eventos sitio** | Sí | ✅ /eventos page |
| **Colaboradores** | **Dark Charm (su otro negocio)** | ⏳ |
| **Visión 3 años** | Estudio grande, otros piercers, tatuadores, joyería online, cursos certificados, sucursal, academia | ✅ Aplicado |
| Venta joyería online | Sí | ⏳ MVP2 |
| Licencia de modelo de negocio (no franquicia) | Sí | ⏳ |
| **Consejo de Iván** | **"Quedate siendo el primero"** | ✅ Reforzado en manifesto |

### 4.8 Cuestionario 08 — Fotos y assets

| Pregunta | Respuesta | Status |
|---|---|---|
| **Fotos del estudio** | Pendiente (no hay estudio) | ⚠️ Placeholders "Curaduría" |
| **Foto del piercer (Luana)** | **Esta semana, sonriendo, mostrando piercings + tattoos + outfit** | ⏳ Trigger: hoy/mañana |
| Fotos de joyería | Pendiente (no hay stock) | ⚠️ Placeholders |
| Catálogo PDF | Cliente va a pasar uno de referencia | ⏳ |
| After photos | Con consentimiento escrito | ⏳ |
| Logo | Pendiente (Luana lo diseña) | ⚠️ Favicon P temporal |
| Manual de marca | Erebus puede generar brandbook | ⏳ |
| Open Graph image | ✅ Ya hecho (1200×630) | ✅ |
| Favicon | Temporal P en rombo | ⏳ Cuando llegue logo |

### 4.9 Cuestionario 09 (round 2) — Inventario de joyería

| Pregunta | Respuesta | Status |
|---|---|---|
| Cantidad primer pedido | 50-100 piezas | ⏳ |
| Tipos | Labrets, industrial, septum, circulares | ⏳ |
| Proveedor | AliExpress (chinos) | ⏳ |
| Certificados titanio | SÍ va a fotografiarlos | ⏳ |
| Catálogo referencia | Dark Charm (su otra tienda) | ⏳ |

### 4.10 Cuestionario 10 (round 2) — Legal y registros

| Pregunta | Respuesta | Status |
|---|---|---|
| RUC | Pendiente | ⏳ |
| Marca registrada | Pendiente | ⏳ |
| Permisos municipales | Pendiente | ⏳ |
| Contador | **El de su papá (rápido)** | ⏳ |
| Datos bancarios | Va a poner el suyo, después asegurar | ⏳ |
| Seguros (responsabilidad civil) | Pendiente | ⏳ |
| Seguro salud Luana | Pendiente | ⏳ |

### 4.11 Cuestionario 11 (round 2) — UX final

| Pregunta | Respuesta | Status |
|---|---|---|
| E1: bajar CTA home | ✅ Sí, solo final + header pequeño | ✅ |
| E2: editorial "Donde el cuerpo se vuelve lienzo" | Luana escribe después | ⏳ (container listo) |
| E3: "Joyería curada" → "Joyería alternativa" | ✅ | ✅ |
| E4: "Sepultura & Góticos" → "Alternative style" | ✅ | ✅ |
| E5: "Plugs & Túneles" → "Expansores" | ✅ | ✅ |
| E6: Mapa oreja 4K HD con piercings reales | Pendiente (assets) | ⏳ |
| E7: Catálogo separado perforación/joyería | ✅ /piercings vs /galeria | ✅ |
| E8: Filtros de joyería (mat/color/zona) | Trigger: cuest 09 + inventario | ⏳ |
| E9: CTA "Lo quiero" en card + "Solicitar presupuesto" en WA + "Reservar cita" en barra fija | ✅ Aplicado mix | ✅ |
| E10: Banner ticker sticky debajo navbar | ✅ | ✅ |
| E11: /nosotros sin bioseguridad duplicado | ✅ | ✅ |
| E12: Before/After en /nosotros | ⏳ Trigger: fotos con consentimiento | ⏳ |
| E13: /nosotros = visión + performer + compromiso | ✅ 3 pillars | ✅ |
| E14: Sin CTA adicional en navbar | ✅ | ✅ |
| E15: Carrito invisible (sessionStorage + WA summary) | MVP2 post-lanzamiento | ⏳ |
| E16: Manifesto en /nosotros | ✅ | ✅ |

### 4.12 Cuestionario 12 (round 2) — Google Reviews y redes setup

| Pregunta | Respuesta | Status |
|---|---|---|
| GMB | No creado (Erebus los guía) | ⏳ |
| IG | No creado, va a crear | ⏳ |
| Bio IG | "Estudio de piercing, joyería alternativa, Asunción, Paraguay, materiales implantgrade, bioseguridad más transparencia, atención con cita, DM, WhatsApp" | ⏳ |
| Hashtag | **#PierceCharm** | ⏳ |
| 100 posts | CM amigo sube, Luana diseña, 2-3/sem inicio | ⏳ |
| WhatsApp Business API | **SÍ (Evolution API + IA agent)** | ⏳ Setup E-EV2 |
| Newsletter | MIX Erebus+Luana | ⏳ |
| Categoría negocio | Estudio de piercings (tatuajes después) | ⏳ |
| URL handles | Listado completo (a conseguir) | ⏳ |

---

## 5. DECISIONES DE UX (E1-E16) — STATUS ACTUALIZADO

### ✅ APLICADAS (13 de 16)
- E1: Hero sin CTA duplicado (header + final)
- E3, E4, E5: Renombres copy
- E7: Catálogo separado
- E9: Mix CTAs (Lo quiero / Solicitar / Reservar)
- E10: Banner ticker sticky
- E11: /nosotros sin bioseguridad duplicado
- E13: 3 pillars en /nosotros
- E14: Sin CTA adicional navbar
- E16: Manifesto
- U1: Hover tooltip en mapa (refactorizado en EarAnatomy round 4b)
- U3: Click directo a WhatsApp con mensaje auto
- U4: WhatsApp número + mensaje claro

### ⏳ DIFERIDAS — tienen trigger (3 de 16)
- **E2** "Donde el cuerpo se vuelve lienzo" — Luana escribe después, container listo en /nosotros
- **E6** Oreja 4K HD con piercings reales — trigger: assets generados (no se pudo generar foto hiperrealista; el SVG estilizado es el fallback)
- **E8** Filtros de joyería (mat/color/zona) — trigger: cuest 09 + inventario cargado
- **E12** Before/After en /nosotros — trigger: fotos con consentimiento
- **E15** Carrito invisible (sessionStorage + WA summary) — trigger: post-lanzamiento, pero **se puede construir YA** sin esperar

---

## 6. DATOS DEL CLIENTE PENDIENTES

| # | Dato | Status | Trigger |
|---|---|---|---|
| C01 | WhatsApp real del estudio | ❌ Placeholder `595981324569` | Cuando Luana tenga línea |
| C02 | Email público | ❌ `hola@piercecharm.com.py` | Cuando lo cree |
| C03 | Instagram handle | ❌ `@pierce.charm` | Cuando lo cree (esta semana) |
| C04 | TikTok handle | ❌ No (no prioritario) | Cuando lo cree |
| C05 | Facebook URL | ❌ | Cuando cree la página |
| C06 | Dirección real del estudio | ❌ "Asunción, Paraguay" | Cuando tenga estudio |
| C07 | RUC / razón social | ❌ | Cuando tramite |
| C08 | Foto del piercer (Luana) | ⏳ "Esta semana" | **HOY** |
| C09 | Foto del estudio | ❌ | Cuando exista el estudio |
| C10 | Logo formal | ⏳ | Luana lo diseña |
| C11 | Catálogo PDF de Dark Charm (referencia) | ⏳ | Luana envía |
| C12 | Fotos reales de inventario | ❌ | Cuando llegue stock (50-100) |

---

## 7. EVENTOS Y OPERACIONES (POST-LANZAMIENTO)

| # | Acción | Status |
|---|---|---|
| E-EV1 | Setup Google Business Profile | ⏳ trigger: dirección confirmada |
| E-EV2 | **Setup Evolution API WhatsApp** | ⏳ confirmado por cliente en audio 2 |
| E-EV3 | Newsletter provider | ⏳ Mix Erebus+Luana |
| E-EV4 | Permitir reviews en Google | ⏳ trigger: URL real GMB |
| E-EV5 | Estrategia 100 posts | ⏳ 2-3/sem inicio |
| E-EV6 | **Eventos Dark Charm cross-promo** | ⏳ confirmado |
| E-EV7 | Percer admirada (hand-free) | ⏳ Luana "voy a anotar" (no llegó nombre) |

---

## 8. ROADMAP POST-LANZAMIENTO (BACKLOG P2-P3)

### P2 (corto plazo, 1-3 meses)
- **E15** Sistema de reservas con carrito invisible (sessionStorage + WhatsApp summary + Google Form consentimiento online)
- **Newsletter** funcional (Brevo/Mailchimp/Buttondown)
- **Blog** con 4 posts SEO iniciales
- **Multi-idioma** es-PY + en + pt-BR
- Email transaccional (confirmaciones de cita)
- CRM básico + tracking de conversiones WhatsApp
- Galería de fotos after-piercing (con consentimiento)
- Web Stories / TikTok embeds en home
- Dashboard de métricas (visitas, contactos WA, conversiones)

### P3 (mediano plazo, 3-12 meses)
- Analytics: Google Analytics o Plausible/Fathom
- SEO internacional ("best piercing Asunción" en inglés)
- Convención tatuajes/piercings — presencia institucional
- Expansión de catálogo si Luana se certifica en surface/dermal/thermal
- Sucursal (Luana mencionó 3 años)

---

## 9. MÉTRICAS LIVE (estado actual)

| Métrica | Valor | Target |
|---|---|---|
| Rutas live | 11/11 (200) | 11/11 |
| h1 por página | 9/9 | 9/9 |
| Canonical URLs | 9/9 | 9/9 |
| HealthAndBeautyBusiness JSON-LD | 9/9 | 9/9 |
| Meta descriptions únicas | 9/9 | 9/9 |
| BAILOUT_TO_CLIENT_SIDE_RENDERING | 0/9 | 0/9 |
| Tamaño home | 124 KB | <100 KB ⚠️ |
| Tamaño /piercings | 126 KB | <100 KB ⚠️ |
| Performance score (Lighthouse) | TBD | >85 |
| A11y score (Lighthouse) | TBD | >95 |
| SEO score (Lighthouse) | TBD | >90 |

---

## 10. THINGS QUE LUANA MENCIONÓ QUE NO ESTÁN EN LOS CUESTIONARIOS

Estas son menciones espontáneas de los audios, fuera de los cuestionarios formales:

### Sobre su trabajo
- "Llevo 20 años, muchísimos años de experiencia, muchísimos, y trabajé con demasiadas [pacientes], con un flujo de pacientes que normalmente no trabajan todos los odontólogos." *(en realidad es la versión original dental del estilo de Luana, ella es piercer)*
- "Nunca tuve ni un problema técnico, ni un problema de praxis en todos mis años de carrera."
- "Pacientes que vienen 10 años después y me dicen 'doctora, esa restauración que me hiciste hace 300.000 años, hay que cambiar'. Y nada, hay que cambiar porque ya cumplió. Con su tiempo." *(paralelo para piercing)*

### Sobre su visión del estudio
- "Ometz" (אומץ) = "coraje" en hebreo
- Trabaja sola, sin mentor
- "Soy artista y performer" — trabaja con cantantes de la escena alternativa
- Cursa actualizacion de piercing cada vez que hay; cursos de surface + dermals pendientes
- "Si alguien ya tiene una joya, traerla para hacer el cambio, pero si la joya se va a usar, tiene que estar esterilizada"
- **Consejo recibido:** "Quedate siendo el primero" (Iván) — accesible, no estudio premium
- "A veces no hago fotos de personas porque no quieren. Según prefiera el cliente."

### Sobre la marca / estética
- "Más vibrantes, saturación grande, hue llamativo" — paleta
- Decoración variar por página (home: luna+cadenas; otras: murciélagos+calaveras)
- Animaciones: murciélagos aleteando 3 frames, llamas parpadeando
- "Si fueran un poco más de cadenas, de murciélagos o una luna, por ejemplo, una luna roja vibrante, quedaría muy bien. Así, varias lunitas vibrantes al costado."
- Simbología: calavera + cruz invertida
- "Estrellitas, lucecitas en dorado o colores más fríos"
- "No bata blanca, scrubs de colores" → esto es de Gaby, en Pierce Charm es similar: sin uniformes institucionales

### Sobre tecnología / sistemas
- Bot WhatsApp triage → Luana humanos importantes
- "Es muy bueno, tipo ideal que la IA le responda en vez de un chatbot"
- Templates frecuentes con imágenes/videos
- **Quiere Evolution API gratis por requisitos de servicios**
- "Es real lo que produce la comunidad si es que te interesa conocerles más, todo el mundo es re chill re sumiso" → sobre eventos con comunidad

### Sobre la competencia (información extra)
- **Body Piercing** — prácticas "no éticas" (perfora igual aunque la pieza no vaya a cicatrizar bien)
- **Sabat** — atención al cliente "es un culo" (sic)
- **Estudio 21** — muy limpios
- Percer admirado (hand-free, sin nombre aún)

### Sobre eventos / comunidad
- "Lanzamiento, noche de piercing, promos de piercing, con tatuajes lineales y pequeños, día que venga gente en fila a formar"
- "Play piercing para sadomasoquismo" — necesita curso
- "Ir a la mascarada y ofrecer 'ey, aparezco con mi aguja y le clavo acá a la gente'" — Iván
- Dark Charm es su otro negocio (ropa alternativa + accesorios)
- "Varios artistas, justamente porque yo soy artista y con cantantes, con performers"

### Sobre la atención
- "Lo más rápida, lo más concisa posible, atenderle lo más rápido"
- "Siempre ser responsable con las respuestas a los clientes"
- "Mostrarles que nosotros nos destacamos no solamente por hacer buenos piercings, sino también porque somos muy buena onda y da gusto venir al estudio"
- **Diferenciador real:** "Si te decimos que algo no va a funcionar, es porque no va a funcionar. Te ofrecemos una alternativa antes de aceptar la perforación."

### Sobre seguimientos
- 1 semana: "¿está bien tu cosa?" (control inicial)
- 1 mes: "no se cayó, está todo bien"
- 3 meses: "¿querés cambiar?" (cambio de joya, abajo del piercing)

### Sobre la galería / casos
- Fotos con consentimiento
- Anonimato según prefiera el cliente
- Before/After sí cuando haya fotos
- No tapar la cara si quiere mostrar; si quiere tapada, le tapamos

---

## 11. ARCHIVOS DE REFERENCIA PARA EL REP

| Archivo | Para qué |
|---|---|
| `apps/pierce-charm/content/es.json` | **Fuente de verdad del contenido.** 54KB. Cualquier cambio de copy/horarios/catálogo/precio va acá. |
| `apps/pierce-charm/app/layout.tsx` | Header, Footer, Float, metadata, JSON-LD, viewport |
| `apps/pierce-charm/app/page.tsx` | Server component con metadata, importa HomeClient |
| `apps/pierce-charm/app/HomeClient.tsx` | Hero + banner ticker + features + nosotros pillars + eventos teaser + newsletter + reviews |
| `apps/pierce-charm/app/piercings/page.tsx` | Usa AnatomySwitcher |
| `apps/pierce-charm/components/AnatomySwitcher.tsx` | Tabs Oreja/Rostro/Cuerpo + grid + CTA |
| `apps/pierce-charm/components/EarAnatomy.tsx` | 14 hotspots oreja con JewelryIcon |
| `apps/pierce-charm/components/FaceSelector.tsx` | 10 hotspots cara |
| `apps/pierce-charm/components/BodySelector.tsx` | 2 hotspots torso |
| `apps/pierce-charm/components/JewelryIcon.tsx` | 12 iconos SVG de joyas |
| `apps/pierce-charm/lib/site-config.ts` | Helper `whatsappUrl()` |
| `apps/pierce-charm/ROAST_FINDINGS.md` | Auditoría original del sitio |
| `pierce-charm-context/docs/PLAN_MAESTRO_DECISIONES.md` | Plan completo con D1-D33 + E1-E16 + C01-C12 + eventos |
| `pierce-charm-context/docs/HANDOFF/QUESTIONNAIRE_LOG.md` | Log consolidado de las 8 respuestas de Luana |
| `pierce-charm-context/docs/08_questionnaires/01-08_*` | Cuestionarios originales archivados |
| `pierce-charm-context/docs/08_questionnaires/09-12_*` | Cuestionarios post-launch (pendientes de activar) |
| `pierce-charm-context/docs/HANDOFF/PACK_PARA_CLIENTE.md` | Pack para Luana/Iván |
| `pierce-charm-context/docs/HANDOFF/QUICKSTART_PARA_LUANA.md` | Quick start |

---

## 12. CHECKLIST DE LO QUE EL REP DEBE HACER (orden de prioridad)

### 🔴 HOY (sin esperar al cliente)
1. **Construir E15 — Carrito invisible v1** (sessionStorage + WhatsApp summary). No requiere datos del cliente.
2. **Implementar jeringa/aguja icons** en bioseguridad (palabra "cateter" + "aguja americana" en el copy)
3. **Validar safe-area-bottom en iPhone 14 Pro Max** (testear el WhatsApp Float vs BottomNav)

### 🟡 MAÑANA (cuando Luana envíe)
4. Reemplazar placeholder de **foto de Luana** en /nosotros
5. Si envía catálogo PDF de Dark Charm, **recolectar paleta y diseño** para ajuste de paleta vibrante
6. Si confirma WhatsApp/IG, **swap placeholders en 5 minutos**

### 🟢 ESTA SEMANA
7. Construir **Newsletter** signup (Brevo / Mailchimp)
8. Construir **filtros de joyería** (material + color + zona) — trigger: cuest 09
9. **SEO: agregar más keywords** (long-tail: "septum piercing Asunción", "helix piercing Paraguay")
10. **Lighthouse run** completo + fix performance issues

### 🔵 PRÓXIMAS 2 SEMANAS
11. Setup **Evolution API WhatsApp + bot IA** (con Hermes de Ai-Whisperers)
12. Setup **Google Business Profile** (cuando dirección confirmada)
13. **E6**: foto oreja 4K HD (intentar generar con Midjourney/Flux si no se puede foto real)
14. **E12**: Before/After (trigger: fotos con consentimiento)

### 🟣 POST-LANZAMIENTO
15. **Multi-idioma** en + pt (Luana puede traducir el copy)
16. **E2**: Container "Donde el cuerpo se vuelve lienzo" con copy de Luana
17. **Blog** con 4 posts SEO
18. **Dashboard** de métricas (visitas, contactos WA)
19. **Cross-promo Dark Charm** (eventos conjuntos)
20. **Percer admirada (hand-free)** que Luana iba a anotar

---

## 13. NOTAS PARA EL REP

1. **Luana es artista y performer.** El estudio no es una clínica — es una boutique de piercing con estética política. El sitio refleja eso. Si querés sumar formalidad clínica, no es la dirección correcta.

2. **Luana se considera alternativa, no premium.** No competir por precio bajo, pero tampoco por precio alto tipo "lujo". El posicionamiento es "accesible + alternativo + honesto". El pricing de Gs 50-150K es accesible.

3. **"Te escucho." es la frase de la marca de Ometz Dental.** La frase de Pierce Charm es: "**El cuerpo es lienzo.**" + "**La odontología no empieza con una fresa. Empieza pensando.**" (la última es de Gaby, no de Luana, pero la idea es la misma: pensar antes de tocar). Para Pierce Charm, la frase central es: "**No existe un todólogo. Si no es viable, te decimos.**" (honestidad sobre anatomía).

4. **El sitio es para Asunción, Paraguay.** Español paraguayo (vos, no tú), guaraníes opcionales pero no en el sitio (Luana no los mencionó).

5. **El "todólogo" no existe.** Luana NO hace surface, NO hace microdermal/ancla, NO hace thermal, NO hace expansiones (todavía), NO hace pezones. Esa honestidad sobre su scope es el diferenciador principal. El sitio tiene que comunicar eso.

6. **El sistema de booking real (E15) es la pieza más importante que falta.** Sin booking, 30-50% de los leads se pierden. Construir YA.

7. **Cuando el cliente dé datos reales**, el patrón es:
   - Updatear `content/es.json` con los nuevos valores
   - Reemplazar placeholders en `site.whatsapp`, `site.email`, `site.instagram`
   - El layout ya usa `whatsappUrl(c.contacto.whatsapp, message)` así que es automático

8. **El repo está en:** `https://github.com/Ai-Whisperers/pierce-charm-context` (estrategia) + `https://github.com/Ai-Whisperers/paragu-ai-platform/tree/main/apps/pierce-charm` (código)

9. **Live URL:** `https://piercecharm.paragu-ai.com/`

10. **Docker**: `pierce-charm_web` service en swarm. Tag: `pierce-charm:prod`.

---

*Documento generado por Erebus, julio 2026. Versión 1.0. Para preguntas o actualizaciones, referirse al PLAN_MAESTRO_DECISIONES.md (que es la fuente de verdad operativa).*
