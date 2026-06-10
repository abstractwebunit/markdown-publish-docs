# Vercel

Le site vit sur `nom.vercel.app` (offre gratuite Hobby).

## Par le bouton

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Vercel créera une copie du [[En quelques clics|template]] dans ton GitHub et construira le site. Les notes sont dans le dossier `vault/`.

## Ton propre dépôt

1. Pose à la racine du dépôt un fichier `vercel.json` :

```json
{
  "buildCommand": "npx --yes @abstractwebunit/markdown-publish build --out dist",
  "outputDirectory": "dist"
}
```

2. Sur [vercel.com/new](https://vercel.com/new), importe ton dépôt → **Deploy**.

À chaque push, le site est reconstruit.

> [!tip] Pas besoin de base-href
> Comme sur [[Netlify]], le site vit à la racine du domaine — le `base-href` par défaut (`/`) convient.

Réglages du site : [[Configuration]].
