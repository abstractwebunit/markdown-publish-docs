# Willkommen

**markdown-publish** verwandelt einen Ordner mit Notizen (einen Obsidian-Vault oder einfach Markdown) in eine schnelle statische Website — so eine wie diese hier. Diese Website wurde damit aus ganz normalen `.md`-Dateien gebaut.

> [!info] Languages / Языки
> [Русский](https://abstractwebunit.github.io/markdown-publish-docs/) · [English](https://abstractwebunit.github.io/markdown-publish-docs/en/) · [Español](https://abstractwebunit.github.io/markdown-publish-docs/es/) · [Deutsch](https://abstractwebunit.github.io/markdown-publish-docs/de/) · [Français](https://abstractwebunit.github.io/markdown-publish-docs/fr/) · [中文](https://abstractwebunit.github.io/markdown-publish-docs/zh/)

> [!tip] Willst du so eine Website mit ein paar Klicks?
> Öffne [[Mit ein paar Klicks]] — dort warten drei Buttons, der Rest läuft von selbst.

## Was es kann

- **[[Suche]]** — blitzschnell, läuft direkt im Browser (drück `Ctrl+K`).
- **[[Linkgraph]]** — eine interaktive Karte deiner Notizen, wie in Obsidian (Link „Graph view“ links).
- **[[Canvas-Boards]]** — `.canvas`-Dateien werden als interaktive Boards gerendert: hier ein [[Karte der Anleitungen.canvas|Live-Beispiel]].
- **[[KI-Agenten (WebMCP)|KI-Agenten]]** — die Website stellt Notizen über WebMCP für KI-Agenten bereit.
- `[[wikilinks]]`, normale Markdown-Links, Embeds, Callouts, Tags, Fußnoten, Code-Highlighting.
- Dunkles/helles Theme, mobile Version, Notiz-Vorschau beim Überfahren eines Links.
- SEO out of the box: sitemap, robots.txt, llms.txt, OG-Karten, JSON-LD.
- Nicht-ASCII-Zeichen in Seitenadressen (Kyrillisch, Umlaute, …) — wie bei dieser Website.

## Wie du deine eigenen Notizen veröffentlichst

| Weg | Aufwand | Anleitung |
|---|---|---|
| Netlify-/Vercel-Button | 2 Klicks | [[Mit ein paar Klicks]] |
| Dein bestehender Vault → GitHub | 10 Minuten, ohne Terminal | [[Dein bestehender Vault auf GitHub]] |
| Template + GitHub Pages | 3–4 Klicks | [[GitHub Pages]] |
| Eigenes Repository + Workflow | für alle, die git kennen | [[GitHub Pages]] |
| Cloudflare Pages | ein paar Minuten | [[Cloudflare Pages]] |
| Lokal über die CLI | Terminal | [[CLI]] |

Veröffentlicht? Dann weiter mit [[Website aktualisieren]]. Alle Einstellungen (Name, Sprache, welche Notizen veröffentlicht werden) findest du in [[Konfiguration]].

## Wo der Code liegt

Das Projekt ist Open Source (MIT): [github.com/abstractwebunit/markdown-publish](https://github.com/abstractwebunit/markdown-publish). Nicht mit Obsidian.MD affiliiert — es liest einfach kompatible Vaults.
