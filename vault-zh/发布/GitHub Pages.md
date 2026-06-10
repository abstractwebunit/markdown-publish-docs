# GitHub Pages

GitHub 提供的免费托管。网站位于 `你的用户名.github.io/仓库名`。

## 通过模板(推荐)

1. 打开[模板](https://github.com/abstractwebunit/markdown-publish-template/generate),给仓库起个名字,点 **Create repository**。
2. 在新仓库里:**Settings → Pages → Source** → 选择 **GitHub Actions**。
3. **Actions** 标签页 → 名为“Publish site”的 workflow → **Run workflow**。
4. 大约 2 分钟后,网站就能通过 `你的用户名.github.io/仓库名` 访问了。

之后:在 `vault/` 里编辑笔记(直接在 GitHub 上或通过 git 都行)——网站会自动重新构建。

## 手动接入自己的仓库

如果笔记已经在你自己的仓库里,添加文件 `.github/workflows/publish.yml`:

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
          site-url: https://你的用户名.github.io/你的仓库名
          base-href: /你的仓库名/
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

把 `你的用户名` 和 `你的仓库名` 替换成实际值,启用 Pages(Settings → Pages → Source: **GitHub Actions**)——搞定。

> [!warning] 最常见的错误——`base-href`
> GitHub Pages 上的网站位于子路径 `/仓库名/`。如果不指定 `base-href: /仓库名/`,页面能打开,但样式和笔记会返回 404。详情:[[常见问题|FAQ]]。

如果 vault 在子文件夹里——在 `with:` 块中加上 `vault-dir: 文件夹名`。全部参数:[[配置]]。
