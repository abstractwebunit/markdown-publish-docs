# Link Graph

An interactive map of all your notes and the links between them — just like in Obsidian.

## Where to find it

- **Global graph** — the "Graph view" link in the sidebar (or open [this site's graph](/graph)).
- **Local graph** — in the right column of every note: the current note and its neighbors. The buttons in its header expand the local or global graph to almost full screen.

## How to use it

- Scroll wheel to zoom, drag the background to pan.
- Drag a node — the physics pulls its neighbors along.
- Hover over a node — it and its neighbors light up while everything else gently fades.
- Click a node to jump to the note.

The more links point to a note, the bigger its node. Labels appear as you zoom in and politely make room for one another.

## Under the hood

Rendering is WebGL: a graph of fifteen hundred notes spins at 60 fps. The layout is computed by a force simulation (d3-force). Links are counted from both `[[wikilinks]]` and regular markdown links between notes.

The graph's connectivity is simply the links between your notes: the more actively you link, the more meaningful the map.
