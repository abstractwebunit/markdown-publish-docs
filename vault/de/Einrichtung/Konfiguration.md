# Konfiguration

Alle Einstellungen der Website leben in einer einzigen Datei — `markdown-publish.config.json` im Root des Repositorys (neben dem Notizen-Ordner).

```json
{
  "siteName": "Meine Notizen",
  "siteDescription": "Mitschriften und Ideen",
  "siteLang": "de",
  "siteUrl": "https://dein-name.github.io/repository",
  "siteFooter": "",
  "vaultDir": "vault",
  "buildMode": "full",
  "baseHref": "/",
  "out": "dist"
}
```

## Was jeder Schlüssel bedeutet

| Schlüssel | Was er tut | Standard |
|---|---|---|
| `siteName` | Name im Header und im `<title>` | Name des Vault-Ordners |
| `siteDescription` | Beschreibung für Suchmaschinen und soziale Netzwerke | — |
| `siteLang` | Sprache des Inhalts (`ru`, `en`, …) | `en` |
| `siteUrl` | Vollständige Adresse der Website — nötig für Sitemap und OG-Karten | — |
| `siteFooter` | Zeile unten in der Sidebar (leer — wird nicht angezeigt) | — |
| `vaultDir` | Ordner mit den Notizen innerhalb des Repositorys | `.` (Root) |
| `buildMode` | `full` — alle Notizen werden veröffentlicht; `public` — nur die mit `publish: public` im Frontmatter | `full` |
| `baseHref` | Unterpfad der Website. Für GitHub Pages — `/repository-name/`, für Netlify/Vercel/Cloudflare — `/` | `/` |
| `out` | Wohin die gebaute Website gelegt wird | `dist` |

## Priorität der Einstellungen

[[CLI]]-Flags übersteuern Umgebungsvariablen, diese die Config-Datei, und die wiederum die Standardwerte.

## Versteckte Notizen

Im Modus `buildMode: public` werden nur Notizen veröffentlicht, die am Dateianfang Folgendes stehen haben:

```markdown
---
publish: public
---
```

Alle anderen landen weder auf der Website noch in der Suche noch im [[Linkgraph|Graph]].

> [!warning] Die größte Stolperfalle — baseHref
> Wenn die Website sich öffnet, aber kaputt aussieht und die Notizen nicht laden — liegt es fast sicher an `baseHref`. Siehe [[FAQ]].
