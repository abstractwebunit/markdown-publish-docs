# Netlify

The site lives at `name.netlify.app` (free tier). The main perk is the button — after it there's literally nothing left to do.

## With the button

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

Netlify will create a copy of the [[In a Couple of Clicks|template]] in your GitHub and build the site right away. Your notes go in the `vault/` folder.

## Your own repository

1. Put a `netlify.toml` file in the repository root:

```toml
[build]
  command = "npx --yes @abstractwebunit/markdown-publish build --out dist"
  publish = "dist"
```

2. On [app.netlify.com](https://app.netlify.com): **Add new site → Import an existing project** → pick your repository → **Deploy**.

Netlify picks up the command from `netlify.toml` by itself. The site rebuilds on every push.

> [!tip] No base-href needed
> On Netlify the site lives at the domain root, so leave `base-href` at its default (`/`) — unlike [[GitHub Pages]].

The site name, language and the rest — via `markdown-publish.config.json` next to `netlify.toml`: [[Configuration]].
