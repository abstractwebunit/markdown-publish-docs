# Suche

Die Suche läuft **komplett im Browser** — ohne Server und ohne dass Anfragen irgendwohin geschickt werden. Der Index ([Pagefind](https://pagefind.app)) wird zusammen mit der Website gebaut und stückweise geladen, deshalb bleibt die Suche auch bei großen Vaults schnell.

## Bedienung

- Klick ins Feld „Search page or heading…“ in der Sidebar — oder drück **Ctrl+K** (`Cmd+K` auf dem Mac).
- Tipp deine Anfrage — die Ergebnisse erscheinen sofort, mit hervorgehobenen Treffern.
- Pfeiltasten ↑/↓ — auswählen, **Enter** — öffnen, **Esc** — schließen.

Probier es gleich aus: Drück `Ctrl+K` und tipp „Konfiguration“.

## Unter der Haube

Beim Build wird jede Seite indexiert, der Index landet neben den statischen Dateien. Im Browser werden nur die gerade benötigten Fragmente des Index nachgeladen — deshalb dauert die erste Suche Millisekunden, statt Megabytes herunterzuladen.

Notizen, die der Modus `public` versteckt ([[Konfiguration]]), kommen nicht in den Index.

Neben der Suche für Menschen gibt es auch eine maschinelle — für KI-Agenten: [[KI-Agenten (WebMCP)]].
