# Dein bestehender Vault auf GitHub

Du hast schon einen Vault voller Notizen (in Obsidian oder einfach einen Ordner mit `.md`-Dateien)? Der Weg ist: **Repository erstellen → Vault hineinlegen → Build verdrahten**. Ganz ohne Terminal.

> [!warning] Entscheide zuerst, was du veröffentlichst
> Die Website enthält **alles, was im Vault liegt** (Standardmodus). Sind manche Notizen privat — kopiere entweder nur den gewünschten Ordner ins Repository, oder aktiviere den `public`-Modus (Schritt 4): dann werden nur Notizen mit der Markierung `publish: public` veröffentlicht.

## Schritt 1 — Repository erstellen

1. Öffne [github.com/new](https://github.com/new).
2. Denk dir einen Namen aus (er wird Teil der Adresse: `dein-name.github.io/name`).
3. Wähle **Public** (öffentlich) — kostenloses GitHub Pages funktioniert nur mit öffentlichen Repositories; brauchst du ein privates Repo, veröffentliche stattdessen über [[Netlify]] oder [[Vercel]] — die bauen private Repos kostenlos.
4. **Create repository**.

## Schritt 2 — Vault hochladen

Ohne git, direkt im Browser:

1. Klick im neuen Repository auf **uploading an existing file** (vorhandene Datei hochladen).
2. Zieh deinen Vault-**Ordner** in den Upload-Bereich (Browser akzeptieren ganze Ordner).
3. **Commit changes**.

> [!tip] Großer Vault?
> Der Web-Uploader nimmt bis zu ~100 Dateien auf einmal. Hast du mehr Notizen — zieh die Unterordner in Etappen hinein, oder installiere [GitHub Desktop](https://desktop.github.com) (ein GUI-Client, kein Terminal): File → Add local repository → Publish.

Empfehlung: Leg die Notizen in einen Ordner `vault/` innerhalb des Repositorys (nicht in die Wurzel) — so vermischen sich Build-Configs nicht mit deinen Notizen.

## Schritt 3 — Build verdrahten

1. Im Repository: **Add file → Create new file**.
2. Tippe ins Namensfeld: `.github/workflows/publish.yml` (die Schrägstriche erzeugen Ordner).
3. Füge den Inhalt der [publish.yml aus dem Template](https://github.com/abstractwebunit/markdown-publish-template/blob/main/.github/workflows/publish.yml) ein — sie übernimmt deinen Benutzernamen und den Repository-Namen automatisch. Liegen deine Notizen nicht in `vault/`, ändere die Zeile `vault-dir: vault` (für die Repository-Wurzel: `vault-dir: .`).
4. **Commit changes**.
5. Pages aktivieren: **Settings → Pages → Source: GitHub Actions**.
6. Tab **Actions** → Workflow „Publish site“ → **Run workflow**.

Nach ~2 Minuten ist die Website unter `dein-name.github.io/repository-name` live. Nächster Halt — [[Website aktualisieren]].

## Schritt 4 — mach sie zu deiner eigenen

Erstelle `markdown-publish.config.json` in der Repository-Wurzel:

```json
{
  "siteName": "Meine Notizen",
  "siteLang": "de",
  "vaultDir": "vault",
  "buildMode": "full"
}
```

- `buildMode: "public"` — veröffentlicht nur Notizen mit `publish: public` im Frontmatter (alles andere bleibt außerhalb der Website, der Suche und des Graphen).
- Alle übrigen Keys: [[Konfiguration]].

> [!note] Soll es noch einfacher gehen?
> Noch kein Vault, oder willst du erst mal nur reinschnuppern — starte mit [[Mit ein paar Klicks|dem Template mit ein paar Klicks]] und zieh deine Notizen später um.
