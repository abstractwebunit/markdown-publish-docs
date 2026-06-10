# Configuration

All the site settings live in a single file — `markdown-publish.config.json` in the repository root (next to the notes folder).

```json
{
  "siteName": "My Notes",
  "siteDescription": "Notes and ideas",
  "siteLang": "en",
  "siteUrl": "https://your-username.github.io/your-repo-name",
  "siteFooter": "",
  "vaultDir": "vault",
  "buildMode": "full",
  "baseHref": "/",
  "out": "dist"
}
```

## What each key means

| Key | What it does | Default |
|---|---|---|
| `siteName` | The name in the header and in `<title>` | the vault folder name |
| `siteDescription` | Description for search engines and social networks | — |
| `siteLang` | Content language (`ru`, `en`, …) | `en` |
| `siteUrl` | The site's full URL — needed for the sitemap and OG cards | — |
| `siteFooter` | A caption at the bottom of the sidebar (empty — not shown) | — |
| `vaultDir` | The notes folder inside the repository | `.` (root) |
| `buildMode` | `full` — all notes are published; `public` — only those with `publish: public` in the frontmatter | `full` |
| `baseHref` | The site's sub-path. For GitHub Pages — `/your-repo-name/`, for Netlify/Vercel/Cloudflare — `/` | `/` |
| `out` | Where to put the built site | `dist` |

## Settings priority

[[CLI]] flags override environment variables, which override the config file, which overrides the defaults.

## Hidden notes

In `buildMode: public` mode, only notes that have this at the top of the file get published:

```markdown
---
publish: public
---
```

The rest won't make it onto the site, into the search, or into the [[Link Graph|graph]].

> [!warning] The number one gotcha — baseHref
> If the site opens but looks broken and notes don't load, it's almost certainly `baseHref`. See [[FAQ]].
