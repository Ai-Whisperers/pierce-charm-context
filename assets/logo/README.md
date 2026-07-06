# Archivos fuente del logo

> Pendiente — el sitio actualmente usa un placeholder SVG (letra "P" en rombo).

Cuando el cliente provea el logo, guardarlo acá en formato:

- `pierce-charm-logo.svg` — versión vectorial principal
- `pierce-charm-logo-mono.svg` — versión monocromática
- `pierce-charm-logo-inverse.svg` — blanco sobre fondo oscuro
- `pierce-charm-favicon.svg` — 32×32 simplificado para favicon
- `pierce-charm-og.png` — 1200×630 para OpenGraph

Y actualizar:
- `apps/pierce-charm/components/Header.tsx` — reemplazar placeholder
- `apps/pierce-charm/components/Footer.tsx` — reemplazar placeholder
- `apps/pierce-charm/app/layout.tsx` — metadata + favicon icon
- `apps/pierce-charm/app/globals.css` — si el logo usa colores adicionales