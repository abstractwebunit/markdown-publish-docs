# Tu vault existente en GitHub

¿Ya tienes un vault lleno de notas (en Obsidian, o simplemente una carpeta de archivos `.md`)? El camino es: **crear un repositorio → poner tu vault dentro → conectar el build**. No hace falta terminal.

> [!warning] Decide primero qué vas a publicar
> El sitio incluirá **todo lo que hay en el vault** (modo por defecto). Si algunas notas son personales — copia al repositorio solo la carpeta que quieras publicar, o activa el modo `public` (paso 4): solo se publican las notas marcadas con `publish: public`.

## Paso 1 — crea un repositorio

1. Abre [github.com/new](https://github.com/new).
2. Elige un nombre (se convierte en la dirección: `username.github.io/nombre`).
3. Marca **Public** (público) — GitHub Pages gratis solo funciona con repositorios públicos; si necesitas un repo privado, publica mediante [[Netlify]] o [[Vercel]]: ellos construyen repos privados gratis.
4. **Create repository** (crear repositorio).

## Paso 2 — sube tu vault

Sin git, directamente en el navegador:

1. En el repositorio nuevo haz clic en **uploading an existing file** (subir un archivo existente).
2. Arrastra la **carpeta** de tu vault a la zona de subida (los navegadores aceptan carpetas enteras).
3. **Commit changes** (confirmar cambios).

> [!tip] ¿Vault grande?
> El cargador web admite hasta ~100 archivos por vez. Si tienes más notas — arrastra las subcarpetas por tandas, o instala [GitHub Desktop](https://desktop.github.com) (un cliente con interfaz gráfica, sin terminal): File → Add local repository → Publish.

Recomendación: guarda las notas en una carpeta `vault/` dentro del repositorio (no en la raíz) — así los configs del build no se mezclan con tus notas.

## Paso 3 — conecta el build

1. En el repositorio: **Add file → Create new file** (añadir archivo → crear archivo nuevo).
2. En el campo del nombre escribe: `.github/workflows/publish.yml` (las barras crean las carpetas).
3. Pega el contenido de [publish.yml de la plantilla](https://github.com/abstractwebunit/markdown-publish-template/blob/main/.github/workflows/publish.yml) — detecta solo tu nombre de usuario y el nombre del repositorio. Si tus notas no están en `vault/`, cambia la línea `vault-dir: vault` (para la raíz del repo usa `vault-dir: .`).
4. **Commit changes**.
5. Activa Pages: **Settings → Pages → Source: GitHub Actions**.
6. Pestaña **Actions** → workflow «Publish site» → **Run workflow**.

En ~2 minutos el sitio está en vivo en `username.github.io/nombre-del-repositorio`. Siguiente parada — [[Cómo actualizar el sitio]].

## Paso 4 — hazlo tuyo

Crea `markdown-publish.config.json` en la raíz del repositorio:

```json
{
  "siteName": "Mis notas",
  "siteLang": "es",
  "vaultDir": "vault",
  "buildMode": "full"
}
```

- `buildMode: "public"` — publica solo las notas con `publish: public` en su frontmatter (todo lo demás queda fuera del sitio, de la búsqueda y del grafo).
- El resto de las claves: [[Configuración]].

> [!note] ¿Lo quieres aún más simple?
> Si todavía no tienes vault, o solo quieres curiosear primero — empieza por [[En un par de clics|la plantilla en un par de clics]] y trae tus notas más tarde.
