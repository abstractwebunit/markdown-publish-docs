# Your Existing Vault on GitHub

Already have a vault full of notes (in Obsidian, or just a folder of `.md` files)? The path is: **create a repository → put your vault in it → wire up the build**. No terminal required.

> [!warning] Decide what you're publishing first
> The site will include **everything in the vault** (default mode). If some notes are personal — either copy only the folder you want into the repository, or enable `public` mode (step 4): only notes marked `publish: public` get published.

## Step 1 — create a repository

1. Open [github.com/new](https://github.com/new).
2. Pick a name (it becomes the address: `username.github.io/name`).
3. Choose **Public** (free GitHub Pages only works with public repositories; if you need a private repo — publish via [[Netlify]] or [[Vercel]] instead, they build private repos for free).
4. **Create repository**.

## Step 2 — upload your vault

No git, right in the browser:

1. In the new repository click **uploading an existing file**.
2. Drag your vault **folder** into the upload area (browsers accept whole folders).
3. **Commit changes**.

> [!tip] Large vault?
> The web uploader takes up to ~100 files at a time. If you have more notes — drag subfolders in batches, or install [GitHub Desktop](https://desktop.github.com) (a GUI client, no terminal): File → Add local repository → Publish.

Recommendation: keep notes in a `vault/` folder inside the repository (not at the root) — build configs won't mix with your notes.

## Step 3 — wire up the build

1. In the repository: **Add file → Create new file**.
2. In the name field type: `.github/workflows/publish.yml` (the slashes create folders).
3. Paste the contents of [publish.yml from the template](https://github.com/abstractwebunit/markdown-publish-template/blob/main/.github/workflows/publish.yml) — it picks up your username and repository name automatically. If your notes aren't in `vault/`, change the `vault-dir: vault` line (for the repo root use `vault-dir: .`).
4. **Commit changes**.
5. Enable Pages: **Settings → Pages → Source: GitHub Actions**.
6. **Actions** tab → «Publish site» workflow → **Run workflow**.

In ~2 minutes the site is live at `username.github.io/repository-name`. Next stop — [[How to Update the Site]].

## Step 4 — make it yours

Create `markdown-publish.config.json` in the repository root:

```json
{
  "siteName": "My Notes",
  "siteLang": "en",
  "vaultDir": "vault",
  "buildMode": "full"
}
```

- `buildMode: "public"` — publish only notes with `publish: public` in their frontmatter (everything else stays out of the site, search and graph).
- All the other keys: [[Configuration]].

> [!note] Want it even simpler?
> No vault yet, or just want to poke around first — start from [[In a Couple of Clicks|the template in a couple of clicks]] and move your notes in later.
