# Round 2 — Aplicado al sitio (2026-07-07 tarde)

Recibida 2da transcripción del mismo diálogo. Esta es la versión **firme + procesada** — todo lo que se pudo aplicar sin consultar antes está en producción.

## Cambios al sitio (live)

### Precios y catálogo (lo más importante)
| Cambio | Antes | Ahora |
|---|---|---|
| **Lóbulo** | Gs 80.000 - Gs 95.000 (3 lóbulos) | **Gs 50.000** todos |
| **Cartílago / faciales** | Gs 120.000 - Gs 160.000 (varío) | **Gs 100.000** uniforme |
| **Industrial + Snug** | Gs 180.000 - Gs 250.000 | **Gs 150.000** (más complejas) |
| **Catálogo total** | 36 perforaciones incluyendo microdermal, surface, thermal, nipple, expansiones | **26 perforaciones reales** — quitamos lo que la piercer NO hace aún |
| **Categorías** | Lóbulo/Cartílago/Industrial/Otros | **Básicos/Cartílago/Faciales/Body/Industrial-orbital** (5 mejor agrupadas) |

### Horarios reales del estudio
| Día | Antes (placeholder) | **Ahora (real)** |
|---|---|---|
| Lunes | Cerrado | **12:00 - 20:00** |
| Martes a Viernes | 14:00 - 20:00 (Vie hasta 21:00) | **12:00 - 20:00** |
| Sábado | 10:00 - 18:00 | **09:00 - 15:00** |
| Domingo | Cerrado | **Cerrado** |

### Copy fixes
- "Joyería curada" → "Joyería alternativa" (en `home.features` y `nosotros.values`)
- /contacto tip de piercing previo reescrito: ahora dice "traéla Esterilizada" (cliente dijo que la versión original no se entendía)
- /contacto WhatsApp CTA ahora manda "Hola! Quiero reservar una cita en Pierce Charm" automáticamente

### Decoración por página (config en `site.page_decor`)
```json
{
  "home":      ["moon", "chain", "gem"],
  "piercings": ["bat", "skull", "flame"],
  "galeria":   ["crescent_moon", "chain", "crown"],
  "nosotros":  ["chain", "bat", "skull"],
  "contacto":  ["flame", "crescent_moon"],
  "faq":       ["skull", "bat"],
}
```

## Decisiones pendientes — NO aplicadas todavía

### Requieren fotos del cliente (post-compra del stock inicial)
- **E12 / E13**: before/after + fotos del estudio + foto de la piercer
- Mapa de oreja con hover de foto real del piercing (no se puede implementar hasta tener fotos)

### Requieren implementar feature nueva
- **E8**: filtros de joyería (material titanio/acero, colores negro/dorado/tornasol, zona oreja/nariz/labio)
- **E15**: carrito invisible → mensaje completo al WhatsApp con todas las piezas elegidas

### Requieren decisión de UX/Ivan (no técnicas)
- **E1**: ¿Bajamos el CTA del home? Por ahora sigue donde estaba
- **E7**: ¿Catálogo separado perforaciones/joyería? Hoy están en 2 páginas separadas (/piercings + /galeria)

### Esperando datos del cliente (no se puede aplicar sin)
- WhatsApp real (vs 595981324569 de Ivan)
- Instagram @handle (vs @pierce.charm placeholder)
- Email real (vs hola@piercecharm.com.py)
- Dirección exacta (vs "Asunción, Paraguay")
- Razón social / RUC

## Lo que sigue inmediatamente (sin esperar más)

1. **Decoración por página**: el `site.page_decor` está como config pero no se está consumiendo en los componentes. Hay que wire-arlo en `ornaments.tsx` o crear un `PageDecor` que lea el config y renderee el set de ornamentos correspondientes a la ruta actual.

2. **Implementar animaciones de murciélagos aleteando** (3 frames): requiere generar 3 PNG de la misma silueta bat en diferentes posiciones de alas, o hacer CSS animation. Más fácil: CSS keyframes con `transform: scaleX()` y rotación alternada.

3. **Color más vibrante**: la paleta actual usa `#d4a843` (gold más vibrante) para accents pero el cliente quiere más saturación. Revisar si los rojos/navy son lo suficientemente vibrantes o empujarlos.

## Commit

- `cbf3b79 feat(pierce-charm): cliente round 2 — horarios reales, precios 50/100/150K, catálogo sin surface, page_decor`

## Estado deploy

- Producción: `https://piercecharm.paragu-ai.com/`
- Imagen Docker: `pierce-charm:prod` 670b2819 → latest
- VPS: 1/1 replicas running
