# AI-агенты (WebMCP)

Сайт умеет отдавать заметки не только людям, но и AI-агентам — структурированно, без выскребания HTML.

## Что это

[WebMCP](https://github.com/webmachinelearning/webmcp) — зарождающийся веб-стандарт (W3C draft): страница регистрирует «инструменты» в `navigator.modelContext`, и AI-агент в браузере может их вызывать. markdown-publish регистрирует четыре:

| Инструмент | Что делает |
|---|---|
| `search_notes(query, limit)` | Поиск по заметкам: заголовок, ссылка, фрагмент |
| `get_note(slug)` | **Полный markdown** заметки + обратные ссылки |
| `list_notes()` | Список всех страниц сайта |
| `get_backlinks(slug)` | Кто ссылается на заметку |

Если у браузера нет нативного `navigator.modelContext`, сайт ставит собственный лёгкий полифилл — без сторонних зависимостей.

## Попробовать руками

Открой DevTools (F12) → Console:

```js
await navigator.modelContext.callTool({
  name: 'search_notes',
  arguments: { query: 'конфигурация', limit: 3 },
})
```

## А ещё для краулеров

- `/llms.txt` — карта сайта для AI-краулеров ([llmstxt.org](https://llmstxt.org)).
- Каждая страница пререндерена в чистый HTML — читается без JavaScript.
- `sitemap.xml`, `robots.txt`, OG-карточки и JSON-LD — обычное SEO тоже на месте.

Скрытые заметки (`buildMode: public`, см. [[Конфигурация]]) агентам не отдаются — их просто нет в сборке.
