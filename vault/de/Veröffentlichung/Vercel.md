# Vercel

Die Website lebt unter `name.vercel.app` (kostenloser Hobby-Tarif).

## Per Button

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Vercel erstellt eine Kopie des [[Mit ein paar Klicks|Templates]] in deinem GitHub und baut die Website. Die Notizen liegen im Ordner `vault/`.

## Eigenes Repository

1. Leg die Datei `vercel.json` ins Root des Repositorys:

```json
{
  "buildCommand": "npx --yes @abstractwebunit/markdown-publish build --out dist",
  "outputDirectory": "dist"
}
```

2. Auf [vercel.com/new](https://vercel.com/new) importiere dein Repository → **Deploy**.

Bei jedem Push wird die Website neu gebaut.

> [!tip] base-href ist nicht nötig
> Wie auf [[Netlify]] lebt die Website im Root der Domain — der Standardwert von `base-href` (`/`) passt.

Einstellungen der Website: [[Konfiguration]].
