# Vercel

El sitio vive en `nombre.vercel.app` (plan gratuito Hobby).

## Con el botón

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Vercel creará una copia de la [[En un par de clics|plantilla]] en tu GitHub y construirá el sitio. Las notas van en la carpeta `vault/`.

## Tu propio repositorio

1. Pon en la raíz del repositorio el archivo `vercel.json`:

```json
{
  "buildCommand": "npx --yes @abstractwebunit/markdown-publish build --out dist",
  "outputDirectory": "dist"
}
```

2. En [vercel.com/new](https://vercel.com/new) importa tu repositorio → **Deploy**.

Con cada push el sitio se reconstruye.

> [!tip] base-href no hace falta
> Igual que en [[Netlify]], el sitio vive en la raíz del dominio — el `base-href` por defecto (`/`) sirve.

Ajustes del sitio: [[Configuración]].
