# GitHub Pages

Hosting gratuito de GitHub. El sitio vive en `tu-usuario.github.io/nombre-del-repositorio`.

## Con la plantilla (recomendado)

1. Abre la [plantilla](https://github.com/abstractwebunit/markdown-publish-template/generate), inventa un nombre para el repositorio y pulsa **Create repository**.
2. En el repositorio nuevo: **Settings → Pages → Source** → elige **GitHub Actions**.
3. Pestaña **Actions** → workflow «Publish site» → **Run workflow**.
4. En ~2 minutos el sitio está disponible en `tu-usuario.github.io/nombre-del-repositorio`.

A partir de ahí: editas las notas en `vault/` (directamente en GitHub o con git) — el sitio se reconstruye solo.

## Manualmente en tu propio repositorio

Si tus notas ya viven en tu repositorio, añade el archivo `.github/workflows/publish.yml`:

```yaml
name: Publish site
on:
  push:
    branches: [main]
  workflow_dispatch:
permissions:
  contents: read
  pages: write
  id-token: write
concurrency:
  group: pages
  cancel-in-progress: true
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: abstractwebunit/markdown-publish@v1
        with:
          site-url: https://ТВОЙ-НИК.github.io/РЕПОЗИТОРИЙ
          base-href: /РЕПОЗИТОРИЙ/
  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - id: deployment
        uses: actions/deploy-pages@v4
```

Sustituye `ТВОЙ-НИК` (tu usuario) y `РЕПОЗИТОРИЙ` (el nombre del repositorio), activa Pages (Settings → Pages → Source: **GitHub Actions**) — listo.

> [!warning] El error más frecuente — `base-href`
> En GitHub Pages el sitio vive en la sub-ruta `/nombre-del-repositorio/`. Si no indicas `base-href: /nombre-del-repositorio/`, las páginas se abrirán, pero los estilos y las notas devolverán 404. Más detalles: [[Preguntas frecuentes]].

Si el vault está en una subcarpeta — añade `vault-dir: nombre-de-la-carpeta` al bloque `with:`. Todos los parámetros: [[Configuración]].
