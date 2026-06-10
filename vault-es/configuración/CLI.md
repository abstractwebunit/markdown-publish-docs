# CLI

Puedes construir el sitio en cualquier máquina con Node.js 20+ — con un solo comando, sin instalar nada:

```bash
npx @abstractwebunit/markdown-publish build --vault путь/к/заметкам --out dist
```

En `dist` aparecerá el sitio estático listo — ábrelo con cualquier servidor de estáticos o súbelo a cualquier hosting.

## Flags

| Flag | Qué hace |
|---|---|
| `--vault <carpeta>` | Ruta al vault (manda sobre todo lo demás) |
| `--vault-dir <carpeta>` | Lo mismo, pero relativa a la carpeta actual o al config |
| `--out <carpeta>` | Dónde construir el sitio (por defecto `dist`) |
| `--config <archivo>` | Ruta al config (por defecto `markdown-publish.config.json`) |
| `--site-name`, `--site-url`, `--site-lang`, `--site-description`, `--site-footer` | Ver [[Configuración]] |
| `--build-mode full\|public` | Publicar todo o solo `publish: public` |
| `--base-href </ruta/>` | Sub-ruta del sitio (para GitHub Pages — `/nombre-del-repositorio/`) |

Los flags mandan sobre el archivo de config, así que puedes mantener los ajustes comunes en `markdown-publish.config.json` y pasar las diferencias por flags.

## Ejemplo: construir y verlo en local

```bash
npx @abstractwebunit/markdown-publish build --vault ./мои-заметки --out site
npx serve site
```

> [!note] Windows + Git Bash
> Git Bash puede «comerse» el valor de `--base-href /sub/` convirtiéndolo en una ruta de Windows. Se cura con el prefijo `MSYS_NO_PATHCONV=1` delante del comando. En PowerShell/cmd normales y en CI esto no pasa.
