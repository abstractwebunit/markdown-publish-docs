# Netlify

Die Website lebt unter `name.netlify.app` (kostenloser Tarif). Der größte Pluspunkt: ein Button, nach dem du überhaupt nichts mehr tun musst.

## Per Button

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

Netlify erstellt eine Kopie des [[Mit ein paar Klicks|Templates]] in deinem GitHub und baut die Website sofort. Die Notizen liegen im Ordner `vault/`.

## Eigenes Repository

1. Leg die Datei `netlify.toml` ins Root des Repositorys:

```toml
[build]
  command = "npx --yes @abstractwebunit/markdown-publish build --out dist"
  publish = "dist"
```

2. Auf [app.netlify.com](https://app.netlify.com): **Add new site → Import an existing project** → wähle dein Repository → **Deploy**.

Netlify übernimmt den Befehl aus `netlify.toml` automatisch. Bei jedem Push wird die Website neu gebaut.

> [!tip] base-href ist nicht nötig
> Auf Netlify lebt die Website im Root der Domain, lass `base-href` also auf dem Standardwert (`/`) — anders als bei [[GitHub Pages]].

Name der Website, Sprache und Co. — über `markdown-publish.config.json` neben der `netlify.toml`: [[Konfiguration]].
