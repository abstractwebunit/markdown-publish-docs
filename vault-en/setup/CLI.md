# CLI

You can build the site on any machine with Node.js 20+ — one command, no install:

```bash
npx @abstractwebunit/markdown-publish build --vault path/to/notes --out dist
```

A ready-to-go static site appears in `dist` — open it with any static server or drop it onto any hosting.

## Flags

| Flag | What it does |
|---|---|
| `--vault <folder>` | Path to the vault (overrides everything) |
| `--vault-dir <folder>` | Same, but relative to the current folder/config |
| `--out <folder>` | Where to build the site (default `dist`) |
| `--config <file>` | Path to the config (default `markdown-publish.config.json`) |
| `--site-name`, `--site-url`, `--site-lang`, `--site-description`, `--site-footer` | See [[Configuration]] |
| `--build-mode full\|public` | Publish everything, or only `publish: public` |
| `--base-href </path/>` | The site's sub-path (for GitHub Pages — `/your-repo-name/`) |

Flags override the config file, so you can keep the shared settings in `markdown-publish.config.json` and pass the differences as flags.

## Example: build and preview locally

```bash
npx @abstractwebunit/markdown-publish build --vault ./my-notes --out site
npx serve site
```

> [!note] Windows + Git Bash
> Git Bash can "eat" the `--base-href /sub/` value by turning it into a Windows path. The fix is prefixing the command with `MSYS_NO_PATHCONV=1`. Plain PowerShell/cmd and CI don't have this problem.
