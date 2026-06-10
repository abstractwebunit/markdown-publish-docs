# Cloudflare Pages

Un CDN muy rápido y un plan gratuito generoso. Cloudflare no tiene botón de un clic para este tipo de proyectos, pero conectarlo lleva un par de minutos.

## Pasos

1. Sube las notas a un repositorio de GitHub (lo más fácil es hacerlo desde la [[En un par de clics|plantilla]]).
2. En el [dashboard de Cloudflare](https://dash.cloudflare.com): **Workers & Pages → Create → Pages → Connect to Git** → elige el repositorio.
3. En los ajustes de build indica:
   - **Build command:** `npx --yes @abstractwebunit/markdown-publish build --out dist`
   - **Build output directory:** `dist`
4. **Save and Deploy**. El sitio recibirá la dirección `nombre.pages.dev`.

Con cada push al repositorio, Cloudflare reconstruye el sitio.

> [!tip] base-href no hace falta
> El sitio vive en la raíz de `*.pages.dev`, así que el `base-href` por defecto (`/`) sirve — a diferencia de [[GitHub Pages]].

El nombre del sitio, el idioma, la descripción — vía `markdown-publish.config.json` en la raíz del repositorio: [[Configuración]].
