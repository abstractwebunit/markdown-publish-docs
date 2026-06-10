# GitHub Pages

Kostenloses Hosting von GitHub. Die Website lebt unter `dein-name.github.io/repository-name`.

## Über das Template (empfohlen)

1. Öffne das [Template](https://github.com/abstractwebunit/markdown-publish-template/generate), denk dir einen Namen für das Repository aus, klick **Create repository**.
2. Im neuen Repository: **Settings → Pages → Source** → wähle **GitHub Actions**.
3. Tab **Actions** → Workflow „Publish site“ → **Run workflow**.
4. Nach ~2 Minuten ist die Website unter `dein-name.github.io/repository-name` erreichbar.

Danach: Du bearbeitest die Notizen in `vault/` (direkt auf GitHub oder per git) — die Website baut sich von selbst neu.

## Manuell in deinem eigenen Repository

Wenn deine Notizen schon in deinem Repository liegen, füge die Datei `.github/workflows/publish.yml` hinzu:

```yaml
name: Publish site
on:
  push:
    branches: [main]
  workflow_dispatch:
permissions:
  contents: read
  pages: write
  id-token: write
concurrency:
  group: pages
  cancel-in-progress: true
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: abstractwebunit/markdown-publish@v1
        with:
          site-url: https://DEIN-NAME.github.io/REPOSITORY
          base-href: /REPOSITORY/
  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - id: deployment
        uses: actions/deploy-pages@v4
```

Ersetze `DEIN-NAME` (deinen GitHub-Namen) und `REPOSITORY` (den Repository-Namen), aktiviere Pages (Settings → Pages → Source: **GitHub Actions**) — fertig.

> [!warning] Der häufigste Fehler — `base-href`
> Eine Website auf GitHub Pages lebt unter dem Unterpfad `/repository-name/`. Gibst du `base-href: /repository-name/` nicht an, öffnen sich die Seiten zwar, aber Styles und Notizen liefern 404. Mehr dazu: [[FAQ]].

Liegt der Vault in einem Unterordner — füge `vault-dir: ordner-name` zum `with:`-Block hinzu. Alle Parameter: [[Konfiguration]].
