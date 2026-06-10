# En un par de clics

El camino más rápido de «una carpeta con notas» a «un sitio en internet». No hace falta instalar nada.

## Opción 1 — el botón de Netlify (la más sencilla)

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

1. Pulsas el botón → entras con GitHub (gratis).
2. Netlify crea por sí solo una copia de la plantilla en tu GitHub y construye el sitio.
3. En un par de minutos el sitio vive en `nombre.netlify.app`.

Después solo pones tus archivos `.md` en la carpeta `vault/` de tu nuevo repositorio — el sitio se reconstruye solo con cada cambio.

## Opción 2 — el botón de Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Lo mismo, pero en Vercel: botón → entrar con GitHub → sitio en `nombre.vercel.app`.

## Opción 3 — plantilla + GitHub Pages (sin servicios de terceros)

Solo hace falta una cuenta de GitHub. Los pasos detallados: [[GitHub Pages]].

[Usar la plantilla →](https://github.com/abstractwebunit/markdown-publish-template/generate)

## Qué hay dentro de la plantilla

El repositorio [markdown-publish-template](https://github.com/abstractwebunit/markdown-publish-template) es:

- `vault/` — tus notas (ya vienen unas cuantas de arranque);
- `markdown-publish.config.json` — los ajustes del sitio ([[Configuración]]);
- configs listos para GitHub Pages, Netlify y Vercel — por eso los botones funcionan.

> [!note] ¿Tus notas ya están en un repositorio?
> Entonces la plantilla no te hace falta — añade el workflow a tu repositorio: [[GitHub Pages#Manualmente en tu propio repositorio]].

## Qué sigue

El sitio ya funciona — ahora mira [[Cómo actualizar el sitio]]: cómo añadir notas (desde el navegador o desde Obsidian) y cómo renombrar el sitio y el repositorio de su nombre aleatorio a algo humano.
