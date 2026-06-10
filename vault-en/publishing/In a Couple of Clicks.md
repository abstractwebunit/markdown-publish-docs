# In a Couple of Clicks

The fastest path from "a folder of notes" to "a site on the internet". Nothing to install.

## Option 1 — the Netlify button (the simplest)

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

1. Press the button → sign in with GitHub (free).
2. Netlify creates a copy of the template in your GitHub by itself and builds the site.
3. A couple of minutes later the site lives at `name.netlify.app`.

From then on you just put your `.md` files into the `vault/` folder of your new repository — the site rebuilds itself on every change.

## Option 2 — the Vercel button

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

The same thing, but on Vercel: button → sign in with GitHub → the site at `name.vercel.app`.

## Option 3 — template + GitHub Pages (no third-party services)

All you need is a GitHub account. Detailed steps: [[GitHub Pages]].

[Use the template →](https://github.com/abstractwebunit/markdown-publish-template/generate)

## What's inside the template

The [markdown-publish-template](https://github.com/abstractwebunit/markdown-publish-template) repository is:

- `vault/` — your notes (a few starter ones are already there);
- `markdown-publish.config.json` — the site settings ([[Configuration]]);
- ready-made configs for GitHub Pages, Netlify and Vercel — that's why the buttons just work.

> [!note] Your notes are already in a repository?
> Then you don't need the template — add the workflow to your own repository: [[GitHub Pages#Manually in your own repository]].

## What's next

The site is up — now see [[How to Update the Site]]: how to add notes (from the browser or from Obsidian) and how to rename the site and the repository from a random name into something human.
