# Mit ein paar Klicks

Der schnellste Weg von „Ordner mit Notizen“ zu „Website im Internet“. Installieren musst du nichts.

## Variante 1 — Netlify-Button (am einfachsten)

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

1. Du klickst den Button → meldest dich über GitHub an (kostenlos).
2. Netlify erstellt selbst eine Kopie des Templates in deinem GitHub und baut die Website.
3. Nach ein paar Minuten lebt die Website unter `name.netlify.app`.

Danach legst du einfach deine `.md`-Dateien in den Ordner `vault/` deines neuen Repositorys — die Website baut sich bei jeder Änderung von selbst neu.

## Variante 2 — Vercel-Button

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Dasselbe, nur auf Vercel: Button → Anmeldung über GitHub → Website unter `name.vercel.app`.

## Variante 3 — Template + GitHub Pages (ohne Drittanbieter)

Du brauchst nur einen GitHub-Account. Die einzelnen Schritte: [[GitHub Pages]].

[Template verwenden →](https://github.com/abstractwebunit/markdown-publish-template/generate)

## Was im Template steckt

Das Repository [markdown-publish-template](https://github.com/abstractwebunit/markdown-publish-template) besteht aus:

- `vault/` — deine Notizen (ein paar Starter-Notizen liegen schon drin);
- `markdown-publish.config.json` — die Einstellungen der Website ([[Konfiguration]]);
- fertigen Configs für GitHub Pages, Netlify und Vercel — deshalb funktionieren die Buttons überhaupt.

> [!note] Deine Notizen liegen schon in einem Repository?
> Dann brauchst du das Template nicht — füge den Workflow in dein Repository ein: [[GitHub Pages#Manuell in deinem eigenen Repository]].

## Wie es weitergeht

Die Website läuft — schau dir jetzt [[Website aktualisieren]] an: wie du Notizen hinzufügst (ob im Browser oder aus Obsidian) und wie du Website und Repository vom zufälligen Namen auf etwas Menschliches umbenennst.
