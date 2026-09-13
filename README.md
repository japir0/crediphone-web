# Crediphone — Landing page (borrador)

Landing de una sola página + página de términos, pensada para GitHub Pages.
Todo lo que ves acá es un punto de partida con datos de ejemplo — está armado
para que sea fácil de editar sin tocar el código.

## Qué es placeholder (buscar "TODO" en los archivos)

- **Número de WhatsApp** (`index.html`, constante `WSP_NUMERO`): hoy dice
  `595900000000`, no es un número real.
- **Logo**: hoy hay un wordmark de texto ("credi**phone**"). Cuando tengas el
  archivo final de tu logo (PNG o SVG), lo subís a `img/` y reemplazamos el
  `<div class="marca">` del header por la imagen.
- **Catálogo y precios** (`data/catalog.json`): modelos, precios y entrega
  inicial son inventados para probar el diseño.
- **Tasa/recargo** (`index.html`, constante `RECARGO_EJEMPLO`, 15%): es un
  número de ejemplo. No lo cambies por la tasa real hasta que esté validada
  legalmente — es justamente el punto que quedó pendiente de resolver con
  el registro OCD/BCP.
- **Fotos de producto**: hoy es un ícono genérico de teléfono
  (`img/phone-placeholder.svg`), dibujado desde cero para no parecerse al
  diseño de ningún modelo real. Cuando tengas fotos reales del inventario,
  reemplazás la ruta `imagen` de cada producto en `catalog.json`.
- **`terminos.html`**: es un esqueleto de secciones, no texto legal. No
  publicar tal cual — necesita revisión de un abogado antes de mostrarse a
  un cliente real, sobre todo la sección de tasa de interés.

## Cómo editar el catálogo

Abrí `data/catalog.json` y agregá/editá productos. No hace falta tocar
`index.html` — el catálogo se carga solo desde ahí. Cada producto necesita:

```json
{
  "id": "identificador-unico",
  "modelo": "iPhone 15",
  "almacenamiento": "128GB",
  "color": "Negro",
  "valorFinanciado": 6300000,
  "entregaInicialPct": 20,
  "imagen": "img/phone-placeholder.svg"
}
```

## Cómo probarlo en tu computadora

Los navegadores bloquean la carga de `data/catalog.json` si abrís
`index.html` directo con doble clic (por seguridad). Para probarlo local,
desde esta carpeta corré:

```
python3 -m http.server 8000
```

y abrí `http://localhost:8000` en el navegador.

## Cómo publicarlo en GitHub Pages (paso a paso)

1. Entrá a github.com con tu cuenta y creá un repositorio nuevo — el botón
   "New" en la esquina superior derecha. Nombre sugerido: `crediphone-web`.
   Dejalo público (GitHub Pages gratis requiere que el repo sea público,
   salvo que tengas GitHub Pro/Team).
2. Subí estos archivos al repo. La forma más simple sin usar la terminal:
   en la página del repo, "Add file" → "Upload files", arrastrás toda esta
   carpeta (manteniendo la estructura `index.html`, `terminos.html`,
   `img/`, `data/`) y confirmás el commit.
3. Andá a **Settings → Pages** dentro del repo.
4. En "Source" elegí la rama `main` y la carpeta `/ (root)`, guardá.
5. GitHub te va a dar una URL tipo `https://tu-usuario.github.io/crediphone-web/`
   — tarda uno o dos minutos en activarse la primera vez.
6. Si más adelante comprás el dominio `crediphone.com.py`, en Settings →
   Pages hay un campo "Custom domain" para apuntarlo ahí.

Si preferís, decime cuando tengas el repo creado y seguimos desde ahí — o si
tenés tu computadora conectada a esta sesión, puedo ayudarte a hacerlo
directo desde el navegador.
