# How to Update the Site

After a [[In a Couple of Clicks|button deploy]], your notes live in **your own GitHub repository** (Netlify/Vercel show a link to it in the site settings). The site rebuilds **itself on every commit** — so update it however you like:

## Way 1 — right in the browser (nothing to install)

1. Open your repository → the `vault/` folder.
2. Click a note → the **Edit** pencil → make your changes → **Commit changes**.
3. New note: **Add file → Create new file** → a name like `My note.md`.

The changes reach the site in ~1–2 minutes (if you don't see them — hard reload, `Ctrl+Shift+R`).

## Way 2 — via Obsidian

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME
```

In Obsidian: **Open folder as vault** → pick the `vault/` folder inside the clone. Write as usual, then commit and push:

```bash
git add -A && git commit -m "notes" && git push
```

> [!tip] Auto-sync
> The **obsidian-git** plugin can commit and push by itself on a schedule — then the site updates "the moment you've written".

## Way 3 — VS Code in the browser

Open your repository on GitHub and press the `.` (dot) key — the github.dev web editor opens: handy for editing lots of files at once.

## Renaming the site and the repository

Netlify creates the repository with a random suffix (something like `markdown-publish-template-61e7d`) — that's normal, and it's fixable:

- **The site name in the header:** the `siteName` key in `markdown-publish.config.json` ([[Configuration]]).
- **The site address:** Netlify → Site configuration → **Change site name** (you'll get `your-name.netlify.app`). On Vercel — Settings → Domains.
- **The repository name:** GitHub → Settings → **Rename**. Netlify/Vercel won't break — GitHub redirects the old name automatically.

## How long does a rebuild take

The first build is the slowest (the hosting downloads the builder). After that it's faster thanks to caching, usually 1–2 minutes. The status is visible in the Deploys tab (Netlify) / Deployments (Vercel/GitHub).
