# Vercel

网站位于 `站点名.vercel.app`(免费的 Hobby 套餐)。

## 用按钮

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Vercel 会在你的 GitHub 里创建[[几次点击搞定|模板]]副本并构建网站。笔记放在 `vault/` 文件夹里。

## 自己的仓库

1. 在仓库根目录放一个 `vercel.json` 文件:

```json
{
  "buildCommand": "npx --yes @abstractwebunit/markdown-publish build --out dist",
  "outputDirectory": "dist"
}
```

2. 在 [vercel.com/new](https://vercel.com/new) 导入你的仓库 → **Deploy**。

每次 push,网站都会重新构建。

> [!tip] 不需要 base-href
> 和 [[Netlify]] 一样,网站位于域名根路径——`base-href` 用默认值(`/`)就行。

网站设置:[[配置]]。
