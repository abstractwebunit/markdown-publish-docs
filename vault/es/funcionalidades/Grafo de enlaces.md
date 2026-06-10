# Grafo de enlaces

Un mapa interactivo de todas las notas y de los enlaces entre ellas — como en Obsidian.

## Dónde verlo

- **Grafo global** — el enlace «Graph view» en la barra lateral (o abre [el grafo de este sitio](/graph)).
- **Grafo local** — en la columna derecha de cada nota: la nota actual y sus vecinas. Los botones de su cabecera despliegan el grafo local o el global casi a pantalla completa.

## Cómo se usa

- Rueda del ratón — zoom; arrastrar el fondo — panorámica.
- Tira de un nodo — la física arrastra a sus vecinos detrás.
- Pasa el cursor por un nodo — él y sus vecinos se resaltan, el resto se atenúa suavemente.
- Clic en un nodo — vas a la nota.

Cuantos más enlaces apuntan a una nota, más grande es su nodo. Las etiquetas aparecen al acercar el zoom y se ceden el sitio unas a otras con elegancia.

## Qué hay bajo el capó

El render es WebGL: un grafo de mil quinientas notas gira a 60 fps. La disposición la calcula una simulación de fuerzas (d3-force). Los enlaces se cuentan tanto de los `[[wikilinks]]` como de los enlaces markdown normales entre notas.

La conectividad del grafo son simplemente los enlaces entre tus notas: cuanto más enlazas, más sentido tiene el mapa.
