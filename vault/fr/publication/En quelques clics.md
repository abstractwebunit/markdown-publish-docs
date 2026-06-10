# En quelques clics

Le chemin le plus rapide entre « un dossier de notes » et « un site en ligne ». Rien à installer.

## Option 1 — le bouton Netlify (le plus simple)

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

1. Tu cliques sur le bouton → tu te connectes via GitHub (gratuit).
2. Netlify crée lui-même une copie du template dans ton GitHub et construit le site.
3. Quelques minutes plus tard, le site vit sur `nom.netlify.app`.

Ensuite, tu déposes simplement tes fichiers `.md` dans le dossier `vault/` de ton nouveau dépôt — le site se reconstruit tout seul à chaque changement.

## Option 2 — le bouton Vercel

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

La même chose, mais chez Vercel : bouton → connexion via GitHub → site sur `nom.vercel.app`.

## Option 3 — template + GitHub Pages (sans services tiers)

Il ne faut qu'un compte GitHub. Les étapes détaillées : [[GitHub Pages]].

[Utiliser le template →](https://github.com/abstractwebunit/markdown-publish-template/generate)

## Ce qu'il y a dans le template

Le dépôt [markdown-publish-template](https://github.com/abstractwebunit/markdown-publish-template), c'est :

- `vault/` — tes notes (quelques notes de départ y sont déjà) ;
- `markdown-publish.config.json` — les réglages du site ([[Configuration]]) ;
- des configs prêtes pour GitHub Pages, Netlify et Vercel — c'est pour ça que les boutons fonctionnent.

> [!note] Tes notes sont déjà dans un dépôt ?
> Alors pas besoin du template — ajoute le workflow à ton dépôt : [[GitHub Pages#Manuellement dans ton propre dépôt]].

## Et ensuite

Le site tourne — passe maintenant à [[Comment mettre à jour le site]] : comment ajouter des notes (depuis le navigateur ou depuis Obsidian) et comment renommer le site et le dépôt pour remplacer le nom aléatoire par quelque chose d'humain.
