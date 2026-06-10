# CLI

Tu peux construire le site sur n'importe quelle machine avec Node.js 20+ — en une seule commande, sans rien installer :

```bash
npx @abstractwebunit/markdown-publish build --vault путь/к/заметкам --out dist
```

(ici `путь/к/заметкам` est le chemin vers ton dossier de notes). Dans `dist` apparaît un site statique prêt à l'emploi — ouvre-le avec n'importe quel serveur statique ou dépose-le chez n'importe quel hébergeur.

## Les flags

| Flag | Ce qu'il fait |
|---|---|
| `--vault <dossier>` | Chemin vers le vault (prioritaire sur tout) |
| `--vault-dir <dossier>` | Pareil, mais relatif au dossier courant/au fichier de config |
| `--out <dossier>` | Où construire le site (par défaut `dist`) |
| `--config <fichier>` | Chemin du fichier de config (par défaut `markdown-publish.config.json`) |
| `--site-name`, `--site-url`, `--site-lang`, `--site-description`, `--site-footer` | Voir [[Configuration]] |
| `--build-mode full\|public` | Publier tout, ou seulement `publish: public` |
| `--base-href </chemin/>` | Sous-chemin du site (pour GitHub Pages : `/nom-du-depot/`) |

Les flags ont priorité sur le fichier de config : tu peux donc garder les réglages communs dans `markdown-publish.config.json` et passer les différences en flags.

## Exemple : construire et regarder en local

```bash
npx @abstractwebunit/markdown-publish build --vault ./мои-заметки --out site
npx serve site
```

> [!note] Windows + Git Bash
> Git Bash peut « avaler » la valeur de `--base-href /sub/` en la transformant en chemin Windows. Le remède : préfixer la commande par `MSYS_NO_PATHCONV=1`. Dans PowerShell/cmd classiques et sur la CI, le problème n'existe pas.
