# AI Agents (WebMCP)

The site can serve notes not only to people but to AI agents too — in a structured way, no HTML scraping required.

## What it is

[WebMCP](https://github.com/webmachinelearning/webmcp) is an emerging web standard (W3C draft): a page registers "tools" in `navigator.modelContext`, and an AI agent in the browser can call them. markdown-publish registers four:

| Tool | What it does |
|---|---|
| `search_notes(query, limit)` | Search across notes: title, link, snippet |
| `get_note(slug)` | The note's **full markdown** + backlinks |
| `list_notes()` | A list of all the site's pages |
| `get_backlinks(slug)` | Who links to a note |

If the browser has no native `navigator.modelContext`, the site installs its own lightweight polyfill — no third-party dependencies.

## Try it yourself

Open DevTools (F12) → Console:

```js
await navigator.modelContext.callTool({
  name: 'search_notes',
  arguments: { query: 'configuration', limit: 3 },
})
```

## And for crawlers too

- `/llms.txt` — a site map for AI crawlers ([llmstxt.org](https://llmstxt.org)).
- Every page is prerendered into clean HTML — readable without JavaScript.
- `sitemap.xml`, `robots.txt`, OG cards and JSON-LD — regular SEO is covered too.

Hidden notes (`buildMode: public`, see [[Configuration]]) are not served to agents — they simply don't exist in the build.
