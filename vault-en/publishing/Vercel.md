# Vercel

The site lives at `name.vercel.app` (the free Hobby tier).

## With the button

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Vercel will create a copy of the [[In a Couple of Clicks|template]] in your GitHub and build the site. Your notes go in the `vault/` folder.

## Your own repository

1. Put a `vercel.json` file in the repository root:

```json
{
  "buildCommand": "npx --yes @abstractwebunit/markdown-publish build --out dist",
  "outputDirectory": "dist"
}
```

2. On [vercel.com/new](https://vercel.com/new) import your repository → **Deploy**.

The site rebuilds on every push.

> [!tip] No base-href needed
> Just like on [[Netlify]], the site lives at the domain root — the default `base-href` (`/`) is what you want.

Site settings: [[Configuration]].
