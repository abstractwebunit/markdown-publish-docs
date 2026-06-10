# GitHub Pages

L'hébergement gratuit de GitHub. Le site vit sur `ton-pseudo.github.io/nom-du-depot`.

## Via le template (recommandé)

1. Ouvre le [template](https://github.com/abstractwebunit/markdown-publish-template/generate), choisis un nom pour le dépôt, clique sur **Create repository**.
2. Dans le nouveau dépôt : **Settings → Pages → Source** → choisis **GitHub Actions**.
3. Onglet **Actions** → workflow « Publish site » → **Run workflow**.
4. Environ 2 minutes plus tard, le site est disponible sur `ton-pseudo.github.io/nom-du-depot`.

Ensuite : tu modifies tes notes dans `vault/` (directement sur GitHub ou via git) — le site se reconstruit tout seul.

## Manuellement dans ton propre dépôt

Si tes notes vivent déjà dans ton dépôt, ajoute le fichier `.github/workflows/publish.yml` :

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
          site-url: https://ТВОЙ-НИК.github.io/РЕПОЗИТОРИЙ
          base-href: /РЕПОЗИТОРИЙ/
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

Remplace `ТВОЙ-НИК` (ton pseudo GitHub) et `РЕПОЗИТОРИЙ` (le nom du dépôt), active Pages (Settings → Pages → Source : **GitHub Actions**) — c'est prêt.

> [!warning] L'erreur la plus fréquente : `base-href`
> Sur GitHub Pages, le site vit sous le sous-chemin `/nom-du-depot/`. Si tu n'indiques pas `base-href: /nom-du-depot/`, les pages s'ouvriront, mais les styles et les notes renverront des 404. Détails : [[FAQ]].

Si le vault est dans un sous-dossier, ajoute `vault-dir: nom-du-dossier` au bloc `with:`. Tous les paramètres : [[Configuration]].
