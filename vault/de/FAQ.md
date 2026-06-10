# FAQ

## Die Website öffnet sich, aber „nackt“: keine Styles, Notizen laden nicht, 404 in der Konsole

Fast immer ist das `baseHref`. Auf GitHub Pages lebt die Website unter dem Unterpfad `/repository-name/`, und der Build muss das wissen:

- im Workflow: `base-href: /repository-name/` (siehe [[GitHub Pages]]);
- auf Netlify/Vercel/Cloudflare lebt die Website im Root — dort lass `/` stehen.

## Ich habe Änderungen deployt, aber die Website zeigt den alten Stand

Der Browser cacht statische Dateien hartnäckig. Drück **Ctrl+Shift+R** (harter Reload) oder öffne die Seite im Inkognito-Fenster. Das gilt besonders für [[Canvas-Boards]] — sie werden als separate Datei geladen.

## Wie verstecke ich einen Teil der Notizen?

`buildMode: public` in [[Konfiguration]] — veröffentlicht werden nur Notizen mit `publish: public` im Frontmatter. Alle anderen landen weder im Build noch in der Suche noch im Graph.

## Sind kyrillische Dateinamen okay?

Ja. Seitenadressen behalten ihre Originalzeichen — Kyrillisch (`/заметки/моя-заметка`) genauso wie deutsche Umlaute —, wie bei Obsidian Publish. Diese Website ist ein lebendes Beispiel.

## Welche Links zwischen Notizen werden verstanden?

Sowohl `[[wikilinks]]` (mit `|Alias`, `#Überschrift`) als auch normale `[Text](andere-notiz.md)`. Beide Arten landen im [[Linkgraph|Graph]] und in den Backlinks.

## Bilder und Anhänge?

Leg sie neben die Notizen und bette sie wie gewohnt ein: `![[bild.png]]` oder `![alt](bild.png)`. Beim Build bekommen die Dateien Hash-Namen und landen auf der Website.

## Was kostet das?

markdown-publish selbst ist kostenlos und Open Source (MIT). GitHub Pages, Netlify, Vercel und Cloudflare Pages haben kostenlose Tarife, die für persönliche Notizen mehr als ausreichen.

## Ist das ein offizielles Obsidian-Produkt?

Nein. Das Projekt ist nicht mit Obsidian.MD affiliiert — es liest einfach das kompatible Format der Vaults und `.canvas`-Dateien (der offene Standard JSON Canvas).

Keine Antwort gefunden? [Stell deine Frage in den Issues](https://github.com/abstractwebunit/markdown-publish/issues).
