# KI-Agenten (WebMCP)

Die Website kann Notizen nicht nur an Menschen ausliefern, sondern auch an KI-Agenten — strukturiert, ohne HTML-Scraping.

## Was das ist

[WebMCP](https://github.com/webmachinelearning/webmcp) ist ein entstehender Webstandard (W3C-Draft): Die Seite registriert „Tools“ in `navigator.modelContext`, und ein KI-Agent im Browser kann sie aufrufen. markdown-publish registriert vier davon:

| Tool | Was es tut |
|---|---|
| `search_notes(query, limit)` | Suche in den Notizen: Titel, Link, Textausschnitt |
| `get_note(slug)` | **Vollständiges Markdown** der Notiz + Backlinks |
| `list_notes()` | Liste aller Seiten der Website |
| `get_backlinks(slug)` | Wer auf die Notiz verlinkt |

Hat der Browser kein natives `navigator.modelContext`, lädt die Website einen eigenen, leichtgewichtigen Polyfill — ohne fremde Abhängigkeiten.

## Selbst ausprobieren

Öffne die DevTools (F12) → Console:

```js
await navigator.modelContext.callTool({
  name: 'search_notes',
  arguments: { query: 'Konfiguration', limit: 3 },
})
```

## Und auch für Crawler

- `/llms.txt` — eine Sitemap für KI-Crawler ([llmstxt.org](https://llmstxt.org)).
- Jede Seite ist in sauberes HTML prerendert — lesbar ganz ohne JavaScript.
- `sitemap.xml`, `robots.txt`, OG-Karten und JSON-LD — klassisches SEO ist ebenfalls an Bord.

Versteckte Notizen (`buildMode: public`, siehe [[Konfiguration]]) bekommen Agenten nicht zu sehen — sie sind schlicht nicht im Build.
