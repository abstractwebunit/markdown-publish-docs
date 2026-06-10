# Agentes de IA (WebMCP)

El sitio sabe entregar las notas no solo a personas, sino también a agentes de IA — de forma estructurada, sin tener que rascar HTML.

## Qué es

[WebMCP](https://github.com/webmachinelearning/webmcp) es un estándar web emergente (borrador del W3C): la página registra «herramientas» en `navigator.modelContext`, y un agente de IA en el navegador puede llamarlas. markdown-publish registra cuatro:

| Herramienta | Qué hace |
|---|---|
| `search_notes(query, limit)` | Búsqueda en las notas: título, enlace, fragmento |
| `get_note(slug)` | **El markdown completo** de la nota + retroenlaces |
| `list_notes()` | Lista de todas las páginas del sitio |
| `get_backlinks(slug)` | Quién enlaza a la nota |

Si el navegador no tiene `navigator.modelContext` nativo, el sitio instala su propio polyfill ligero — sin dependencias de terceros.

## Pruébalo con tus propias manos

Abre DevTools (F12) → Console:

```js
await navigator.modelContext.callTool({
  name: 'search_notes',
  arguments: { query: 'конфигурация', limit: 3 },
})
```

## Y también para los crawlers

- `/llms.txt` — un mapa del sitio para crawlers de IA ([llmstxt.org](https://llmstxt.org)).
- Cada página está prerenderizada en HTML limpio — se lee sin JavaScript.
- `sitemap.xml`, `robots.txt`, tarjetas OG y JSON-LD — el SEO de toda la vida también está en su sitio.

Las notas ocultas (`buildMode: public`, ver [[Configuración]]) no se entregan a los agentes — simplemente no existen en la build.
