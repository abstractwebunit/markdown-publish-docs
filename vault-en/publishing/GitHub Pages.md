# GitHub Pages

Free hosting from GitHub. The site lives at `your-username.github.io/repo-name`.

## Via the template (recommended)

1. Open the [template](https://github.com/abstractwebunit/markdown-publish-template/generate), pick a name for the repository, press **Create repository**.
2. In the new repository: **Settings → Pages → Source** → choose **GitHub Actions**.
3. The **Actions** tab → the "Publish site" workflow → **Run workflow**.
4. About 2 minutes later the site is available at `your-username.github.io/repo-name`.

After that: edit notes in `vault/` (right on GitHub or via git) — the site rebuilds itself.

## Manually in your own repository

If your notes already live in your own repository, add a `.github/workflows/publish.yml` file:

```yaml
name: Publish site
on:
  push:
    branches: [main]
  workflow_dispatch:
permissions:
  contents: read
  pages: write
  id-token: write
concurrency:
  group: pages
  cancel-in-progress: true
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: abstractwebunit/markdown-publish@v1
        with:
          site-url: https://YOUR-USERNAME.github.io/YOUR-REPO-NAME
          base-href: /YOUR-REPO-NAME/
  deploy:
    needs: build
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - id: deployment
        uses: actions/deploy-pages@v4
```

Replace `YOUR-USERNAME` (your GitHub username) and `YOUR-REPO-NAME` (your repository name), enable Pages (Settings → Pages → Source: **GitHub Actions**) — done.

> [!warning] The most common mistake — `base-href`
> A site on GitHub Pages lives under the sub-path `/your-repo-name/`. If you don't set `base-href: /your-repo-name/`, the pages will open, but the styles and notes will return 404. More details: [[FAQ]].

If your vault sits in a subfolder — add `vault-dir: folder-name` to the `with:` block. All the parameters: [[Configuration]].
