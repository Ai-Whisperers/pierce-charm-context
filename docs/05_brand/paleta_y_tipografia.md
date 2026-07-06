# Paleta y tipografía — Pierce Charm

## Paleta acordada

| Color | HEX | Uso |
|---|---|---|
| Burgundy / sangre | `#63081d` | Primary — CTAs, acentos principales |
| Midnight indigo | `#211b54` | Secondary — fondos oscuros |
| Royal purple | `#520b4e` | Accent — bordes brillantes, highlights |
| Gold (decorativo) | `#b08838` | Ornamentos, cruces invertidas, gemas |

## Derivadas construidas en CSS

```css
--color-primary:        #63081d;   /* base */
--color-primary-deep:   #3a040f;   /* sombras */
--color-primary-light:  #8b1a31;   /* hover, glows */

--color-secondary:       #211b54;  /* base */
--color-secondary-deep:  #0f0c2e;  /* sombras profundas */
--color-secondary-light: #3a3380;  /* hover */

--color-accent:        #520b4e;    /* base */
--color-accent-deep:   #2e052a;    /* sombras */
--color-accent-light:  #7a2673;    /* hover */

--color-gold:       #b08838;       /* decoración */
--color-gold-soft:  #2c2014;       /* gold con fondo oscuro */
```

## Fondos

| Token | HEX | Uso |
|---|---|---|
| `--color-background` | `#0a0612` | Body, secciones oscuras |
| `--color-surface` | `#14091f` | Cards en fondo primary |
| `--color-surface-light` | `#1f1230` | Cards elevados |
| `--color-card` | `#1a0e25` | Background card hover |

## Tipografía

| Rol | Familia | Uso |
|---|---|---|
| Display | **Cinzel** 400-700 | h1, h2, h3, eyebrows, botones |
| Script | **Tangerine** 400-700 | Acentos cursivos decorativos (𓆩 frase 𓆪) |
| Body | **Inter** 300-700 | Párrafos, captions |

### Por qué estas tipografías

- **Cinzel** evoca inscripciones romanas / góticas; sus capitales con tracking amplio funcionan para el tono "medieval dark".
- **Tangerine** aporta contraste cursivo humanista — perfecto para detalles decorativos tipo manuscrito.
- **Inter** es nuestra elección estándar para legibilidad en mobile.

## Mood board (referencia estética)

- Tiendas dark/gothic similares a las que el cliente admiraba (referencias pendientes)
- Estética witch-house / alt-fashion
- Tattoo studios oscuros como `jota-ink-tattoo`
- Simbolismo: cadenas, calaveras, murciélagos, cruces invertidas, velas, arañas, luna creciente

## Tokens en `content/tokens.json`

La paleta también está duplicada en `apps/pierce-charm/content/tokens.json` del sitio web para que pueda ser consumida por componentes sin hardcodear HEX.