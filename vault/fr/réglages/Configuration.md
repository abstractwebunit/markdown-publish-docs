# Configuration

Tous les réglages du site vivent dans un seul fichier : `markdown-publish.config.json`, à la racine du dépôt (à côté du dossier de notes).

```json
{
  "siteName": "Мои заметки",
  "siteDescription": "Конспекты и идеи",
  "siteLang": "ru",
  "siteUrl": "https://ник.github.io/репозиторий",
  "siteFooter": "",
  "vaultDir": "vault",
  "buildMode": "full",
  "baseHref": "/",
  "out": "dist"
}
```

## Ce que signifie chaque clé

| Clé | Ce qu'elle fait | Par défaut |
|---|---|---|
| `siteName` | Le nom dans l'en-tête et dans le `<title>` | le nom du dossier du vault |
| `siteDescription` | La description pour les moteurs de recherche et les réseaux sociaux | — |
| `siteLang` | La langue du contenu (`ru`, `en`, …) | `en` |
| `siteUrl` | L'adresse complète du site — nécessaire pour le sitemap et les cartes OG | — |
| `siteFooter` | La signature en bas de la barre latérale (vide = masquée) | — |
| `vaultDir` | Le dossier des notes dans le dépôt | `.` (la racine) |
| `buildMode` | `full` : toutes les notes sont publiées ; `public` : seulement celles avec `publish: public` dans le frontmatter | `full` |
| `baseHref` | Le sous-chemin du site. Pour GitHub Pages : `/nom-du-depot/`, pour Netlify/Vercel/Cloudflare : `/` | `/` |
| `out` | Où poser le site construit | `dist` |

## Priorité des réglages

Les flags de la [[CLI]] ont priorité sur les variables d'environnement, qui ont priorité sur le fichier de config, qui a priorité sur les valeurs par défaut.

## Notes masquées

En mode `buildMode: public`, seules sont publiées les notes qui commencent par :

```markdown
---
publish: public
---
```

Les autres n'apparaîtront ni sur le site, ni dans la recherche, ni dans le [[Graphe de liens|graphe]].

> [!warning] Le piège numéro un : baseHref
> Si le site s'ouvre mais a l'air cassé et que les notes ne se chargent pas, c'est presque à coup sûr `baseHref`. Voir la [[FAQ]].
