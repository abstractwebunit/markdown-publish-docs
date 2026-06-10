# Netlify

网站位于 `站点名.netlify.app`(免费套餐)。最大的优点是有个按钮,点完之后什么都不用做。

## 用按钮

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

Netlify 会在你的 GitHub 里创建[[几次点击搞定|模板]]副本并立刻构建网站。笔记放在 `vault/` 文件夹里。

## 自己的仓库

1. 在仓库根目录放一个 `netlify.toml` 文件:

```toml
[build]
  command = "npx --yes @abstractwebunit/markdown-publish build --out dist"
  publish = "dist"
```

2. 在 [app.netlify.com](https://app.netlify.com):**Add new site → Import an existing project** → 选择你的仓库 → **Deploy**。

Netlify 会自动读取 `netlify.toml` 里的命令。每次 push,网站都会重新构建。

> [!tip] 不需要 base-href
> 在 Netlify 上,网站位于域名根路径,所以 `base-href` 保持默认值(`/`)即可——这一点和 [[GitHub Pages]] 不同。

网站名称、语言等设置——通过 `netlify.toml` 旁边的 `markdown-publish.config.json`:[[配置]]。
