# Comment mettre à jour le site

Après le [[En quelques clics|déploiement par bouton]], tes notes vivent dans **ton dépôt GitHub** (Netlify/Vercel affichent le lien vers lui dans les réglages du site). Le site se reconstruit **tout seul à chaque commit** — tu peux donc le mettre à jour comme ça t'arrange :

## Méthode 1 — directement dans le navigateur (rien à installer)

1. Ouvre ton dépôt → le dossier `vault/`.
2. Clique sur une note → le crayon **Edit** → modifie → **Commit changes**.
3. Nouvelle note : **Add file → Create new file** → un nom du genre `Ma note.md`.

Au bout d'environ 1–2 minutes, les changements sont sur le site (si tu ne les vois pas — rechargement forcé, `Ctrl+Shift+R`).

## Méthode 2 — via Obsidian

```bash
git clone https://github.com/ТВОЙ-НИК/ТВОЙ-РЕПОЗИТОРИЙ
```

(remplace `ТВОЙ-НИК` et `ТВОЙ-РЕПОЗИТОРИЙ` par ton pseudo GitHub et le nom de ton dépôt). Dans Obsidian : **Open folder as vault** → choisis le dossier `vault/` à l'intérieur du clone. Tu écris comme d'habitude, puis commit et push :

```bash
git add -A && git commit -m "notes" && git push
```

> [!tip] Synchronisation automatique
> Le plugin **obsidian-git** sait commiter et pusher tout seul selon un planning — le site se met alors à jour « à peine la note écrite ».

## Méthode 3 — VS Code dans le navigateur

Ouvre le dépôt sur GitHub et appuie sur la touche `.` (point) — l'éditeur web github.dev s'ouvre : pratique pour modifier plein de fichiers d'un coup.

## Renommer le site et le dépôt

Netlify crée le dépôt avec un suffixe aléatoire (du genre `markdown-publish-template-61e7d`) — c'est normal, et ça se soigne :

- **Le nom du site dans l'en-tête :** la clé `siteName` dans `markdown-publish.config.json` ([[Configuration]]).
- **L'adresse du site :** Netlify → Site configuration → **Change site name** (tu obtiendras `ton-nom.netlify.app`). Chez Vercel : Settings → Domains.
- **Le nom du dépôt :** GitHub → Settings → **Rename**. Netlify/Vercel ne casseront pas — GitHub redirige automatiquement l'ancien nom.

## Combien de temps prend la reconstruction

Le premier build est le plus long (l'hébergeur télécharge le générateur). Ensuite, c'est plus rapide grâce au cache, en général 1–2 minutes. Le statut est visible dans l'onglet Deploys (Netlify) / Deployments (Vercel/GitHub).
