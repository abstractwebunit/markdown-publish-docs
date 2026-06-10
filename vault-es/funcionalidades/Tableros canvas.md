# Tableros canvas

Los archivos `.canvas` (el formato [JSON Canvas](https://jsoncanvas.org) que usa Obsidian) se renderizan como tableros interactivos.

Ejemplo en vivo: [[Mapa de guías.canvas|Mapa de guías]] — está en este vault como un archivo `.canvas` normal.

## Qué se soporta

- **Tarjetas de texto** — el markdown de dentro se renderiza al completo.
- **Tarjetas de nota** — muestran el contenido de una nota; un clic la abre.
- **Tarjetas de enlace** — enlaces externos con título.
- **Grupos** — marcos con etiqueta.
- **Flechas** entre tarjetas, con etiquetas.

## Interactividad

- Rueda del ratón — zoom; arrastrar el fondo — panorámica; al abrirse, el tablero se ajusta solo a la pantalla.
- Las tarjetas se pueden **arrastrar** (las flechas las siguen) y **redimensionar** por el borde derecho/inferior o por la esquina.
- Los cambios viven hasta que recargas la página — el sitio es estático, el `.canvas` original no se modifica.

El tablero aparece en la navegación de la izquierda como una página normal.
