# Cloudflare Pages

Un CDN très rapide, une offre gratuite généreuse. Cloudflare n'a pas de bouton en un clic pour ce type de projet, mais le branchement prend deux minutes.

## Les étapes

1. Pousse tes notes dans un dépôt GitHub (le plus simple : partir du [[En quelques clics|template]]).
2. Dans le [dashboard Cloudflare](https://dash.cloudflare.com) : **Workers & Pages → Create → Pages → Connect to Git** → choisis ton dépôt.
3. Dans les réglages du build, indique :
   - **Build command :** `npx --yes @abstractwebunit/markdown-publish build --out dist`
   - **Build output directory :** `dist`
4. **Save and Deploy**. Le site recevra une adresse `nom.pages.dev`.

À chaque push dans le dépôt, Cloudflare reconstruit le site.

> [!tip] Pas besoin de base-href
> Le site vit à la racine de `*.pages.dev`, donc le `base-href` par défaut (`/`) convient — contrairement à [[GitHub Pages]].

Le nom du site, la langue, la description : via `markdown-publish.config.json` à la racine du dépôt : [[Configuration]].
