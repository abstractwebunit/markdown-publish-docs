# Preguntas frecuentes

## El sitio se abre, pero «desnudo»: sin estilos, las notas no cargan, 404 en la consola

Casi siempre es `baseHref`. En GitHub Pages el sitio vive en la sub-ruta `/nombre-del-repositorio/`, y la build tiene que saberlo:

- en el workflow: `base-href: /nombre-del-repositorio/` (ver [[GitHub Pages]]);
- en Netlify/Vercel/Cloudflare el sitio vive en la raíz — ahí deja `/`.

## Desplegué cambios, pero el sitio muestra lo de antes

El navegador cachea los archivos estáticos con uñas y dientes. Pulsa **Ctrl+Shift+R** (recarga forzada) o ábrelo en una ventana de incógnito. Esto aplica sobre todo a los [[Tableros canvas|tableros canvas]] — se cargan como un archivo aparte.

## ¿Cómo oculto una parte de las notas?

`buildMode: public` en [[Configuración]] — solo se publican las notas con `publish: public` en el frontmatter. El resto no entra ni en la build, ni en la búsqueda, ni en el grafo.

## ¿Los nombres de archivo en cirílico están bien?

Sí. Las URL de las páginas conservan el cirílico (`/заметки/моя-заметка`), igual que en Obsidian Publish. Lo mismo vale para los acentos — este sitio es un ejemplo vivo.

## ¿Qué enlaces entre notas se entienden?

Tanto los `[[wikilinks]]` (con `|alias` y `#encabezado`) como los normales `[texto](otra-nota.md)`. Ambos tipos entran en el [[Grafo de enlaces|grafo]] y en los retroenlaces.

## ¿Imágenes y adjuntos?

Ponlos junto a las notas e insértalos como siempre: `![[imagen.png]]` o `![alt](imagen.png)`. Durante la build los archivos reciben nombres con hash y llegan al sitio.

## ¿Cuánto cuesta?

markdown-publish en sí es gratuito y de código abierto (MIT). GitHub Pages, Netlify, Vercel y Cloudflare Pages tienen planes gratuitos que sobran de largo para unas notas personales.

## ¿Es un producto oficial de Obsidian?

No. El proyecto no está afiliado a Obsidian.MD — simplemente lee el formato compatible de vaults y de archivos `.canvas` (el estándar abierto JSON Canvas).

¿No encontraste la respuesta? [Haz tu pregunta en los issues](https://github.com/abstractwebunit/markdown-publish/issues).
