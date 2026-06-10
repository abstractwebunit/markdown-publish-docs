# Tableaux Canvas

Les fichiers `.canvas` (le format [JSON Canvas](https://jsoncanvas.org) qu'utilise Obsidian) sont rendus comme des tableaux interactifs.

Exemple vivant : la [[Carte des guides.canvas|Carte des guides]] — c'est un simple fichier `.canvas` posé dans ce vault.

## Ce qui est pris en charge

- **Cartes de texte** — le markdown à l'intérieur est rendu intégralement.
- **Cartes-notes** — affichent le contenu d'une note ; un clic l'ouvre.
- **Cartes-liens** — des liens externes avec leur titre.
- **Groupes** — des cadres avec une étiquette.
- **Flèches** entre les cartes, avec des étiquettes.

## Interactivité

- Molette : zoom ; glisser le fond : panoramique ; à l'ouverture, le tableau s'ajuste tout seul à l'écran.
- Les cartes peuvent être **déplacées** (les flèches suivent) et **redimensionnées** par le bord droit/bas ou par le coin.
- Les réagencements vivent jusqu'au rechargement de la page — le site est statique, le fichier `.canvas` d'origine ne change pas.

Le tableau apparaît dans la navigation de gauche comme une page normale.
