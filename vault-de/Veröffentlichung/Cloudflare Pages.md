# Cloudflare Pages

Sehr schnelles CDN, großzügiger kostenloser Tarif. Einen Ein-Klick-Button hat Cloudflare für diese Art von Projekten zwar nicht, aber das Anbinden dauert nur ein paar Minuten.

## Schritte

1. Lade deine Notizen in ein GitHub-Repository hoch (am einfachsten — aus dem [[Mit ein paar Klicks|Template]]).
2. Im [Cloudflare-Dashboard](https://dash.cloudflare.com): **Workers & Pages → Create → Pages → Connect to Git** → wähle das Repository.
3. In den Build-Einstellungen gib an:
   - **Build command:** `npx --yes @abstractwebunit/markdown-publish build --out dist`
   - **Build output directory:** `dist`
4. **Save and Deploy**. Die Website bekommt eine Adresse wie `name.pages.dev`.

Bei jedem Push ins Repository baut Cloudflare die Website neu.

> [!tip] base-href ist nicht nötig
> Die Website lebt im Root von `*.pages.dev`, der Standardwert von `base-href` (`/`) passt also — anders als bei [[GitHub Pages]].

Name der Website, Sprache, Beschreibung — über `markdown-publish.config.json` im Root des Repositorys: [[Konfiguration]].
