# Cloudflare Pages

A very fast CDN with a generous free tier. Cloudflare has no one-click button for this kind of project, but hooking it up takes a couple of minutes.

## Steps

1. Push your notes to a GitHub repository (the easiest way — from the [[In a Couple of Clicks|template]]).
2. In the [Cloudflare dashboard](https://dash.cloudflare.com): **Workers & Pages → Create → Pages → Connect to Git** → pick the repository.
3. In the build settings set:
   - **Build command:** `npx --yes @abstractwebunit/markdown-publish build --out dist`
   - **Build output directory:** `dist`
4. **Save and Deploy**. The site gets the address `name.pages.dev`.

On every push to the repository, Cloudflare rebuilds the site.

> [!tip] No base-href needed
> The site lives at the root of `*.pages.dev`, so the default `base-href` (`/`) is fine — unlike [[GitHub Pages]].

The site name, language, description — via `markdown-publish.config.json` in the repository root: [[Configuration]].
