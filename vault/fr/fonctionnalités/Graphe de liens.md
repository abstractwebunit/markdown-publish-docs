# Graphe de liens

Une carte interactive de toutes les notes et des liens entre elles — comme dans Obsidian.

## Où le voir

- **Graphe global** — le lien « Graph view » dans la barre latérale (ou ouvre [le graphe de ce site](/graph)).
- **Graphe local** — dans la colonne de droite de chaque note : la note courante et ses voisines. Les boutons dans son en-tête déploient le graphe local ou global presque en plein écran.

## Comment l'utiliser

- Molette : zoom ; glisser le fond : panoramique.
- Tire un nœud — la physique entraîne ses voisins à sa suite.
- Survole un nœud — lui et ses voisins s'illuminent, le reste s'estompe en douceur.
- Clique sur un nœud — tu arrives sur la note.

Plus une note reçoit de liens, plus son nœud est gros. Les étiquettes apparaissent quand on zoome et se cèdent poliment la place les unes aux autres.

## Sous le capot

Le rendu est en WebGL : un graphe de mille cinq cents notes tourne à 60 fps. La disposition est calculée par une simulation de forces (d3-force). Les liens sont comptés aussi bien depuis les `[[wikilinks]]` que depuis les liens markdown classiques entre notes.

La connectivité du graphe, ce sont simplement les liens entre tes notes : plus tu lies activement, plus la carte a de sens.
