# Recherche

La recherche fonctionne **entièrement dans le navigateur** — sans serveur et sans envoyer la moindre requête où que ce soit. L'index ([Pagefind](https://pagefind.app)) est construit en même temps que le site et chargé par morceaux, donc elle reste rapide même sur de gros vaults.

## Comment l'utiliser

- Clique dans le champ « Search page or heading… » de la barre latérale — ou appuie sur **Ctrl+K** (`Cmd+K` sur Mac).
- Tape ta requête — les résultats apparaissent à la volée, avec les correspondances en surbrillance.
- Flèches ↑/↓ : sélection, **Enter** : ouvrir, **Esc** : fermer.

Essaie tout de suite : appuie sur `Ctrl+K` et tape « configuration ».

## Sous le capot

Au build, chaque page est indexée et l'index est posé à côté des fichiers statiques. Le navigateur ne charge que les fragments d'index nécessaires — c'est pourquoi la première recherche prend des millisecondes au lieu de télécharger des mégaoctets.

Les notes masquées par le mode `public` ([[Configuration]]) n'entrent pas dans l'index.

En plus de la recherche pour les humains, le site en a une pour les machines — les agents IA : [[Agents IA (WebMCP)]].
