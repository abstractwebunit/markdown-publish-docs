# FAQ

## Le site s'ouvre, mais il est « tout nu » : pas de styles, les notes ne se chargent pas, des 404 dans la console

C'est presque toujours `baseHref`. Sur GitHub Pages, le site vit sous un sous-chemin `/nom-du-depot/`, et le build doit le savoir :

- dans le workflow : `base-href: /nom-du-depot/` (voir [[GitHub Pages]]) ;
- sur Netlify/Vercel/Cloudflare, le site vit à la racine — là, laisse `/`.

## J'ai déployé des changements, mais le site affiche l'ancienne version

Le navigateur met les fichiers statiques en cache avec acharnement. Fais **Ctrl+Shift+R** (rechargement forcé) ou ouvre le site en navigation privée. C'est particulièrement vrai pour les [[Tableaux Canvas|tableaux canvas]] — ils sont chargés dans un fichier séparé.

## Comment masquer une partie des notes ?

`buildMode: public` dans [[Configuration]] — seules les notes avec `publish: public` dans le frontmatter sont publiées. Les autres n'apparaissent ni dans le build, ni dans la recherche, ni dans le graphe.

## Les noms de fichiers en cyrillique (ou avec des accents), ça passe ?

Oui. Les adresses de pages conservent les caractères tels quels (`/заметки/моя-заметка`), comme avec Obsidian Publish. Ce site, avec ses dossiers accentués comme « réglages » et « fonctionnalités », en est un exemple vivant.

## Quels liens entre notes sont compris ?

Les `[[wikilinks]]` (avec `|alias`, `#titre`) comme les liens classiques `[texte](autre-note.md)`. Les deux types alimentent le [[Graphe de liens|graphe]] et les rétroliens.

## Et les images et pièces jointes ?

Pose-les à côté de tes notes et insère-les comme d'habitude : `![[image.png]]` ou `![alt](image.png)`. Au build, les fichiers reçoivent des noms hachés et sont copiés sur le site.

## Combien ça coûte ?

markdown-publish lui-même est gratuit et open source (MIT). GitHub Pages, Netlify, Vercel et Cloudflare Pages ont des offres gratuites largement suffisantes pour des notes personnelles.

## C'est un produit officiel d'Obsidian ?

Non. Le projet n'est pas affilié à Obsidian.MD — il lit simplement le format compatible des vaults et des fichiers `.canvas` (le standard ouvert JSON Canvas).

Tu n'as pas trouvé ta réponse ? [Pose ta question dans les issues](https://github.com/abstractwebunit/markdown-publish/issues).
