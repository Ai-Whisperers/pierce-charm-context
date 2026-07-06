# Brief original — Pierce Charm

> **Fecha:** 2026-07-06
> **Recibido vía:** WhatsApp (texto)
> **Quién lo dio:** Cliente directo (Ivan en nombre del estudio)

## Lo que el cliente quiere

### Negocio
- Tienda que **hace piercings y vende joyas**
- Ubicación: Asunción, Paraguay
- Modelo: estudio profesional con venta de joyería curada

### Nombre
- **Pierce Charm**

### Contenido del sitio
1. **Nombre del negocio** + presentación breve
2. **Sobre el negocio**: qué es, qué hace
3. **Galería de piercings** con:
   - Imágenes de la oreja con la posición del piercing
   - Nombre de cada ejemplo
   - **Función interactiva:** que los clientes puedan elegir un piercing y presupuestar la cita

### Estética obligatoria
- Paleta de colores:
  - `#63081d` (burdeos / sangre)
  - `#211b54` (índigo medianoche)
  - `#520b4e` (púrpura real)
- Variantes y mezclas de estos colores son bienvenidas
- Estética política alternativa
- **Decoraciones:** cadenas, murciélagos, calaveras, etc.
- Las decoraciones pueden ser:
  - Elementos no interactivos a los costados
  - Emojis en textos

## Análisis de sitios previos

> Indicado por el cliente: analizar las páginas web creadas anteriormente para saber qué partes utilizar y qué quedan bien con la temática.

Sitios de referencia (Ai-Whisperers):
- `paragu-ai-builder/sites/` — todos los sitios generados
- `template-nextjs-client` — template base
- `jota-ink-tattoo` — tattoo studio, paralelo cercano
- `dra-gabriela`, `magnolia-peluqueria`, `portas-barber`, `shine-nails` — servicios personales

## Decisiones tomadas inmediatamente

| Pregunta | Respuesta |
|---|---|
| ¿Stack? | Next.js (como todos los sitios AiW) |
| ¿Modo oscuro? | **Sí** — la paleta pide fondo oscuro (los 3 HEX son oscuros) |
| ¿Decoraciones laterales? | **Sí** — cadenas en costados desktop, murciélagos flotando |
| ¿Emojis? | **Sí** — sutilmente en eyebrows y separadores (𓆩 ☆ 𓆪 ⚜ ✦ 💀) |
| ¿Selector de piercing con presupuesto? | **Sí** — earmap interactivo + cards por tipo con precio |
| ¿WhatsApp como CTA principal? | **Sí** — número del cliente como destination |

## Tareas iniciales

- [x] Construir sitio completo con la paleta + estética dark/gothic
- [x] 6 rutas: home, piercings, galería, nosotros, contacto, FAQ
- [x] Mapa interactivo de oreja con hotspots por piercing
- [x] Catálogo de 19 tipos de piercing con precio, descripción, tiempo de cicatrización
- [x] Galería de 12 piezas de joyería curada
- [x] 8 preguntas frecuentes
- [x] Layout responsive mobile-first con bottom-nav
- [ ] Agregar fotos reales del estudio (cliente debe proveer)
- [ ] Agregar fotos reales de las piezas de joyería
- [ ] Confirmar horarios reales del estudio
- [ ] Confirmar barrio y dirección del estudio
- [ ] Confirmar Instagram handle real
- [ ] Confirmar email real

## Notas adicionales del cliente

- Idioma del sitio: **español (es-PY)**
- Moneda: **Guaraníes (Gs.)** en los precios
- Tono de comunicación: profesional pero con personalidad alternativa/política
- No quieren ser "otra peluquería" — quieren destacar la estética y la postura