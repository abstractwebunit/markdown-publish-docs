# Configuración

Todos los ajustes del sitio viven en un solo archivo — `markdown-publish.config.json` en la raíz del repositorio (junto a la carpeta de notas).

```json
{
  "siteName": "Мои заметки",
  "siteDescription": "Конспекты и идеи",
  "siteLang": "ru",
  "siteUrl": "https://ник.github.io/репозиторий",
  "siteFooter": "",
  "vaultDir": "vault",
  "buildMode": "full",
  "baseHref": "/",
  "out": "dist"
}
```

## Qué significa cada clave

| Clave | Qué hace | Por defecto |
|---|---|---|
| `siteName` | El nombre en la cabecera y en el `<title>` | el nombre de la carpeta del vault |
| `siteDescription` | Descripción para buscadores y redes sociales | — |
| `siteLang` | Idioma del contenido (`ru`, `en`, …) | `en` |
| `siteUrl` | Dirección completa del sitio — hace falta para el sitemap y las tarjetas OG | — |
| `siteFooter` | Texto al pie de la barra lateral (vacío — no se muestra) | — |
| `vaultDir` | Carpeta con las notas dentro del repositorio | `.` (la raíz) |
| `buildMode` | `full` — se publican todas las notas; `public` — solo las que tienen `publish: public` en el frontmatter | `full` |
| `baseHref` | Sub-ruta del sitio. Para GitHub Pages — `/nombre-del-repositorio/`, para Netlify/Vercel/Cloudflare — `/` | `/` |
| `out` | Dónde dejar el sitio construido | `dist` |

## Prioridad de los ajustes

Los flags de la [[CLI]] mandan sobre las variables de entorno, estas sobre el archivo de config, y este sobre los valores por defecto.

## Notas ocultas

En el modo `buildMode: public` solo se publican las notas que al principio del archivo llevan:

```markdown
---
publish: public
---
```

El resto no llegará ni al sitio, ni a la búsqueda, ni al [[Grafo de enlaces|grafo]].

> [!warning] El tropiezo número uno — baseHref
> Si el sitio se abre pero se ve roto y las notas no cargan — casi seguro que es cosa del `baseHref`. Ver [[Preguntas frecuentes]].
