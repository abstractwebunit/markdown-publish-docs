# Agents IA (WebMCP)

Le site sait servir les notes non seulement aux humains, mais aussi aux agents IA — de façon structurée, sans avoir à gratter du HTML.

## C'est quoi

[WebMCP](https://github.com/webmachinelearning/webmcp) est un standard web naissant (draft W3C) : la page enregistre des « outils » dans `navigator.modelContext`, et un agent IA dans le navigateur peut les appeler. markdown-publish en enregistre quatre :

| Outil | Ce qu'il fait |
|---|---|
| `search_notes(query, limit)` | Recherche dans les notes : titre, lien, extrait |
| `get_note(slug)` | **Le markdown complet** de la note + ses rétroliens |
| `list_notes()` | La liste de toutes les pages du site |
| `get_backlinks(slug)` | Qui pointe vers la note |

Si le navigateur n'a pas de `navigator.modelContext` natif, le site installe son propre polyfill léger — sans dépendances tierces.

## Essayer à la main

Ouvre les DevTools (F12) → Console :

```js
await navigator.modelContext.callTool({
  name: 'search_notes',
  arguments: { query: 'конфигурация', limit: 3 },
})
```

## Et aussi pour les crawlers

- `/llms.txt` — un plan du site pour les crawlers IA ([llmstxt.org](https://llmstxt.org)).
- Chaque page est pré-rendue en HTML propre — lisible sans JavaScript.
- `sitemap.xml`, `robots.txt`, cartes OG et JSON-LD — le SEO classique est aussi au rendez-vous.

Les notes masquées (`buildMode: public`, voir [[Configuration]]) ne sont pas servies aux agents — elles n'existent tout simplement pas dans le build.
