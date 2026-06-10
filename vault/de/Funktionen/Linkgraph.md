# Linkgraph

Eine interaktive Karte aller Notizen und der Links zwischen ihnen — wie in Obsidian.

## Wo du ihn findest

- **Globaler Graph** — der Link „Graph view“ in der Sidebar (oder öffne den [Graph dieser Website](/graph)).
- **Lokaler Graph** — in der rechten Spalte jeder Notiz: die aktuelle Notiz und ihre Nachbarn. Die Buttons in seiner Kopfzeile vergrößern den lokalen oder den globalen Graph fast auf den ganzen Bildschirm.

## Bedienung

- Mausrad — Zoom, Hintergrund ziehen — Panorama.
- Zieh an einem Knoten — die Physik zieht die Nachbarn mit.
- Fahre über einen Knoten — er und seine Nachbarn leuchten auf, der Rest blendet sanft aus.
- Klick auf einen Knoten — Sprung zur Notiz.

Je mehr Links auf eine Notiz zeigen, desto größer ihr Knoten. Beschriftungen erscheinen beim Heranzoomen und machen einander ordentlich Platz.

## Unter der Haube

Gerendert wird mit WebGL: Ein Graph aus anderthalbtausend Notizen läuft mit 60 fps. Das Layout berechnet eine Force-Simulation (d3-force). Als Links zählen sowohl `[[wikilinks]]` als auch normale Markdown-Links zwischen Notizen.

Die Vernetzung des Graphen sind einfach die Links zwischen deinen Notizen: Je fleißiger du verlinkst, desto aussagekräftiger die Karte.
