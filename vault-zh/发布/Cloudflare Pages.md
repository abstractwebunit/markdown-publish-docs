# Cloudflare Pages

非常快的 CDN,免费套餐很慷慨。Cloudflare 对这类项目没有一键按钮,但接入也只需要几分钟。

## 步骤

1. 把笔记上传到 GitHub 仓库(最简单的办法是用[[几次点击搞定|模板]])。
2. 在 [Cloudflare 控制台](https://dash.cloudflare.com):**Workers & Pages → Create → Pages → Connect to Git** → 选择仓库。
3. 在构建设置里填写:
   - **Build command:** `npx --yes @abstractwebunit/markdown-publish build --out dist`
   - **Build output directory:** `dist`
4. **Save and Deploy**。网站会得到地址 `站点名.pages.dev`。

每次向仓库 push,Cloudflare 都会重新构建网站。

> [!tip] 不需要 base-href
> 网站位于 `*.pages.dev` 的根路径,所以默认的 `base-href`(`/`)就够用了——这一点和 [[GitHub Pages]] 不同。

网站名称、语言、描述——通过仓库根目录的 `markdown-publish.config.json`:[[配置]]。
