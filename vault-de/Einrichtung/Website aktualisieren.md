# Website aktualisieren

Nach dem [[Mit ein paar Klicks|Deploy per Button]] leben deine Notizen in **deinem GitHub-Repository** (Netlify/Vercel zeigen den Link darauf in den Website-Einstellungen). Die Website wird **bei jedem Commit automatisch neu gebaut** — aktualisieren kannst du also, wie es dir am liebsten ist:

## Weg 1 — direkt im Browser (ohne irgendetwas zu installieren)

1. Öffne dein Repository → Ordner `vault/`.
2. Klick auf eine Notiz → Stift **Edit** → bearbeiten → **Commit changes**.
3. Neue Notiz: **Add file → Create new file** → ein Name wie `Meine Notiz.md`.

Nach ~1–2 Minuten sind die Änderungen auf der Website (wenn nicht — harter Reload, `Ctrl+Shift+R`).

## Weg 2 — über Obsidian

```bash
git clone https://github.com/DEIN-NAME/DEIN-REPOSITORY
```

(Ersetze `DEIN-NAME`/`DEIN-REPOSITORY` durch deinen GitHub-Namen und den Namen deines Repositorys.) In Obsidian: **Open folder as vault** → wähle den Ordner `vault/` im Klon. Schreib wie gewohnt, danach Commit und Push:

```bash
git add -A && git commit -m "notes" && git push
```

> [!tip] Automatische Synchronisation
> Das Plugin **obsidian-git** kann selbstständig nach Zeitplan committen und pushen — dann aktualisiert sich die Website, „sobald du geschrieben hast“.

## Weg 3 — VS Code im Browser

Öffne das Repository auf GitHub und drück die Taste `.` (Punkt) — es öffnet sich der Web-Editor github.dev: praktisch, um viele Dateien auf einmal zu bearbeiten.

## Website und Repository umbenennen

Netlify legt das Repository mit einem zufälligen Suffix an (etwa `markdown-publish-template-61e7d`) — das ist normal und lässt sich beheben:

- **Name der Website im Header:** der Schlüssel `siteName` in `markdown-publish.config.json` ([[Konfiguration]]).
- **Adresse der Website:** Netlify → Site configuration → **Change site name** (ergibt `dein-name.netlify.app`). Bei Vercel — Settings → Domains.
- **Name des Repositorys:** GitHub → Settings → **Rename**. Netlify/Vercel gehen dabei nicht kaputt — GitHub leitet den alten Namen automatisch weiter.

## Wie lange dauert der Rebuild

Der erste Build dauert am längsten (das Hosting lädt den Builder herunter). Danach geht es dank Cache schneller, meist 1–2 Minuten. Den Status siehst du im Tab Deploys (Netlify) / Deployments (Vercel/GitHub).
