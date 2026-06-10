# Cómo actualizar el sitio

Después del [[En un par de clics|deploy con el botón]] tus notas viven en **tu repositorio de GitHub** (Netlify/Vercel muestran el enlace en los ajustes del sitio). El sitio se reconstruye **solo con cada commit** — así que actualízalo como te resulte más cómodo:

## Método 1 — directamente en el navegador (sin instalar nada)

1. Abre tu repositorio → carpeta `vault/`.
2. Haz clic en una nota → el lápiz **Edit** → edita → **Commit changes**.
3. Nota nueva: **Add file → Create new file** → un nombre tipo `Mi nota.md`.

En ~1–2 minutos los cambios están en el sitio (si no se ven — recarga forzada, `Ctrl+Shift+R`).

## Método 2 — con Obsidian

```bash
git clone https://github.com/ТВОЙ-НИК/ТВОЙ-РЕПОЗИТОРИЙ
```

En Obsidian: **Open folder as vault** → elige la carpeta `vault/` dentro del clon. Escribes como siempre, y luego commit y push:

```bash
git add -A && git commit -m "notes" && git push
```

> [!tip] Autosincronización
> El plugin **obsidian-git** sabe hacer commit y push él solo, según un horario — así el sitio se actualiza «en cuanto terminas de escribir».

## Método 3 — VS Code en el navegador

Abre el repositorio en GitHub y pulsa la tecla `.` (punto) — se abrirá el editor web github.dev: cómodo para editar muchos archivos de golpe.

## Renombrar el sitio y el repositorio

Netlify crea el repositorio con un sufijo aleatorio (del tipo `markdown-publish-template-61e7d`) — es normal, y tiene arreglo:

- **El nombre del sitio en la cabecera:** la clave `siteName` en `markdown-publish.config.json` ([[Configuración]]).
- **La dirección del sitio:** Netlify → Site configuration → **Change site name** (quedará `tu-nombre.netlify.app`). En Vercel — Settings → Domains.
- **El nombre del repositorio:** GitHub → Settings → **Rename**. Netlify/Vercel no se rompen — GitHub redirige el nombre antiguo automáticamente.

## Cuánto tarda la reconstrucción

La primera build es la más larga (el hosting descarga el builder). Las siguientes van más rápido gracias a la caché, normalmente 1–2 minutos. El estado se ve en la pestaña Deploys (Netlify) / Deployments (Vercel/GitHub).
