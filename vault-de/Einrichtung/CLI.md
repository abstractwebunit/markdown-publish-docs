# CLI

Die Website lässt sich auf jeder Maschine mit Node.js 20+ bauen — mit einem einzigen Befehl, ganz ohne Installation:

```bash
npx @abstractwebunit/markdown-publish build --vault pfad/zu/den-notizen --out dist
```

In `dist` liegt danach die fertige statische Website — öffne sie mit einem beliebigen Static-Server oder lad sie auf ein beliebiges Hosting hoch.

## Flags

| Flag | Was es tut |
|---|---|
| `--vault <Ordner>` | Pfad zum Vault (übersteuert alles) |
| `--vault-dir <Ordner>` | Dasselbe, aber relativ zum aktuellen Ordner/zur Config |
| `--out <Ordner>` | Wohin die Website gebaut wird (Standard: `dist`) |
| `--config <Datei>` | Pfad zur Config (Standard: `markdown-publish.config.json`) |
| `--site-name`, `--site-url`, `--site-lang`, `--site-description`, `--site-footer` | Siehe [[Konfiguration]] |
| `--build-mode full\|public` | Alles veröffentlichen oder nur `publish: public` |
| `--base-href </pfad/>` | Unterpfad der Website (für GitHub Pages — `/repository-name/`) |

Flags übersteuern die Config-Datei — du kannst also gemeinsame Einstellungen in `markdown-publish.config.json` halten und Abweichungen per Flag übergeben.

## Beispiel: bauen und lokal ansehen

```bash
npx @abstractwebunit/markdown-publish build --vault ./meine-notizen --out site
npx serve site
```

> [!note] Windows + Git Bash
> Git Bash kann den Wert von `--base-href /sub/` „verschlucken“ und in einen Windows-Pfad verwandeln. Abhilfe schafft das Präfix `MSYS_NO_PATHCONV=1` vor dem Befehl. In normalem PowerShell/cmd und auf CI passiert das nicht.
