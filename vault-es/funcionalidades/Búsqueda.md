# Búsqueda

La búsqueda funciona **por completo en el navegador** — sin servidor y sin enviar consultas a ninguna parte. El índice ([Pagefind](https://pagefind.app)) se genera junto con el sitio y se carga por trocitos, así que es rápida incluso en vaults grandes.

## Cómo se usa

- Haz clic en el campo «Search page or heading…» de la barra lateral — o pulsa **Ctrl+K** (`Cmd+K` en Mac).
- Escribe la consulta — los resultados aparecen al vuelo, con las coincidencias resaltadas.
- Flechas ↑/↓ — elegir, **Enter** — abrir, **Esc** — cerrar.

Pruébalo ahora mismo: pulsa `Ctrl+K` y escribe «configuración».

## Qué hay bajo el capó

Durante la build cada página se indexa y el índice se deja junto a los estáticos. En el navegador solo se cargan los fragmentos del índice que hacen falta — por eso la primera búsqueda tarda milisegundos en vez de descargar megabytes.

Las notas ocultas por el modo `public` ([[Configuración]]) no entran en el índice.

Además de la búsqueda para humanos, el sitio tiene una para máquinas — para agentes de IA: [[Agentes de IA (WebMCP)]].
