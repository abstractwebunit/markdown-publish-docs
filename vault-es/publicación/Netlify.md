# Netlify

El sitio vive en `nombre.netlify.app` (plan gratuito). Su gran ventaja es el botón tras el cual no hay que hacer absolutamente nada más.

## Con el botón

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

Netlify creará una copia de la [[En un par de clics|plantilla]] en tu GitHub y construirá el sitio de inmediato. Las notas van en la carpeta `vault/`.

## Tu propio repositorio

1. Pon en la raíz del repositorio el archivo `netlify.toml`:

```toml
[build]
  command = "npx --yes @abstractwebunit/markdown-publish build --out dist"
  publish = "dist"
```

2. En [app.netlify.com](https://app.netlify.com): **Add new site → Import an existing project** → elige tu repositorio → **Deploy**.

Netlify tomará solo el comando de `netlify.toml`. Con cada push el sitio se reconstruye.

> [!tip] base-href no hace falta
> En Netlify el sitio vive en la raíz del dominio, así que deja el `base-href` por defecto (`/`) — a diferencia de [[GitHub Pages]].

El nombre del sitio, el idioma y lo demás — vía `markdown-publish.config.json` junto a `netlify.toml`: [[Configuración]].
