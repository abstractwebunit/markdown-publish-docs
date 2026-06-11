# Ton vault existant sur GitHub

Tu as déjà un vault rempli de notes (dans Obsidian, ou simplement un dossier de fichiers `.md`) ? Le chemin : **créer un dépôt → y mettre ton vault → brancher le build**. Aucun terminal nécessaire.

> [!warning] Décide d'abord ce que tu publies
> Le site inclura **tout le contenu du vault** (mode par défaut). Si certaines notes sont personnelles — copie seulement le dossier voulu dans le dépôt, ou active le mode `public` (étape 4) : seules les notes marquées `publish: public` seront publiées.

## Étape 1 — créer un dépôt

1. Ouvre [github.com/new](https://github.com/new).
2. Choisis un nom (il devient l'adresse : `username.github.io/name`).
3. Sélectionne **Public** (la version gratuite de GitHub Pages ne fonctionne qu'avec des dépôts publics ; s'il te faut un dépôt privé — publie plutôt via [[Netlify]] ou [[Vercel]], ils buildent les dépôts privés gratuitement).
4. **Create repository** (créer le dépôt).

## Étape 2 — téléverser ton vault

Sans git, directement dans le navigateur :

1. Dans le nouveau dépôt, clique sur **uploading an existing file** (téléverser un fichier existant).
2. Glisse le **dossier** de ton vault dans la zone de dépôt (les navigateurs acceptent des dossiers entiers).
3. **Commit changes** (valider les changements).

> [!tip] Un gros vault ?
> L'uploader web accepte environ 100 fichiers à la fois. Si tu as plus de notes — glisse les sous-dossiers par lots, ou installe [GitHub Desktop](https://desktop.github.com) (un client graphique, sans terminal) : File → Add local repository → Publish.

Recommandation : garde tes notes dans un dossier `vault/` à l'intérieur du dépôt (pas à la racine) — les fichiers de configuration du build ne se mélangeront pas avec tes notes.

## Étape 3 — brancher le build

1. Dans le dépôt : **Add file → Create new file**.
2. Dans le champ du nom, tape : `.github/workflows/publish.yml` (les barres obliques créent les dossiers).
3. Colle le contenu de [publish.yml du template](https://github.com/abstractwebunit/markdown-publish-template/blob/main/.github/workflows/publish.yml) — il récupère automatiquement ton nom d'utilisateur et le nom du dépôt. Si tes notes ne sont pas dans `vault/`, modifie la ligne `vault-dir: vault` (pour la racine du dépôt, mets `vault-dir: .`).
4. **Commit changes**.
5. Active Pages : **Settings → Pages → Source: GitHub Actions**.
6. Onglet **Actions** → workflow « Publish site » → **Run workflow**.

En ~2 minutes, le site est en ligne à l'adresse `username.github.io/repository-name`. Prochaine étape — [[Comment mettre à jour le site]].

## Étape 4 — personnalise-le

Crée `markdown-publish.config.json` à la racine du dépôt :

```json
{
  "siteName": "Mes notes",
  "siteLang": "fr",
  "vaultDir": "vault",
  "buildMode": "full"
}
```

- `buildMode: "public"` — ne publie que les notes avec `publish: public` dans leur frontmatter (tout le reste reste hors du site, de la recherche et du graphe).
- Toutes les autres clés : [[Configuration]].

> [!note] Tu veux encore plus simple ?
> Pas encore de vault, ou envie d'explorer d'abord — commence par [[En quelques clics|le template en quelques clics]] et déplace tes notes plus tard.
