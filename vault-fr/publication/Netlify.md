# Netlify

Le site vit sur `nom.netlify.app` (offre gratuite). Le gros avantage : un bouton après lequel il n'y a vraiment plus rien à faire.

## Par le bouton

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

Netlify créera une copie du [[En quelques clics|template]] dans ton GitHub et construira aussitôt le site. Les notes sont dans le dossier `vault/`.

## Ton propre dépôt

1. Pose à la racine du dépôt un fichier `netlify.toml` :

```toml
[build]
  command = "npx --yes @abstractwebunit/markdown-publish build --out dist"
  publish = "dist"
```

2. Sur [app.netlify.com](https://app.netlify.com) : **Add new site → Import an existing project** → choisis ton dépôt → **Deploy**.

Netlify récupérera lui-même la commande depuis `netlify.toml`. À chaque push, le site est reconstruit.

> [!tip] Pas besoin de base-href
> Sur Netlify, le site vit à la racine du domaine, donc laisse le `base-href` par défaut (`/`) — contrairement à [[GitHub Pages]].

Le nom du site, la langue et le reste : via `markdown-publish.config.json` à côté de `netlify.toml` : [[Configuration]].
