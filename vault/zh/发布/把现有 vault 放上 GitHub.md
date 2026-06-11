# 把现有 vault 放上 GitHub

已经有一个装满笔记的 vault(Obsidian 的,或者就是一个装 `.md` 文件的文件夹)?路径是:**创建仓库 → 把 vault 放进去 → 接好构建**。全程不需要终端。

> [!warning] 先决定要发布什么
> 网站会包含 **vault 里的所有内容**(默认模式)。如果有些笔记是私人的——要么只把想发布的文件夹复制进仓库,要么开启 `public` 模式(第 4 步):只有标记了 `publish: public` 的笔记才会被发布。

## 第 1 步——创建仓库

1. 打开 [github.com/new](https://github.com/new)。
2. 取一个名字(它会成为网址:`username.github.io/name`)。
3. 选择 **Public**(公开)——免费的 GitHub Pages 只对公开仓库有效;如果需要私有仓库,改用 [[Netlify]] 或 [[Vercel]] 发布,它们可以免费构建私有仓库。
4. **Create repository**(创建仓库)。

## 第 2 步——上传你的 vault

不用 git,直接在浏览器里操作:

1. 在新仓库里点击 **uploading an existing file**(上传现有文件)。
2. 把你的 vault **文件夹**拖进上传区域(浏览器支持拖入整个文件夹)。
3. **Commit changes**(提交更改)。

> [!tip] vault 很大?
> 网页上传器一次最多接收约 100 个文件。笔记更多的话——分批拖入子文件夹,或者安装 [GitHub Desktop](https://desktop.github.com)(图形客户端,无需终端):File → Add local repository → Publish。

建议:把笔记放在仓库内的 `vault/` 文件夹里(而不是根目录)——这样构建配置不会和笔记混在一起。

## 第 3 步——接好构建

1. 在仓库里:**Add file → Create new file**(添加文件 → 新建文件)。
2. 在文件名输入框里输入:`.github/workflows/publish.yml`(斜杠会自动创建文件夹)。
3. 粘贴[模板里的 publish.yml](https://github.com/abstractwebunit/markdown-publish-template/blob/main/.github/workflows/publish.yml) 的内容——它会自动识别你的用户名和仓库名。如果笔记不在 `vault/` 里,修改 `vault-dir: vault` 这一行(笔记在仓库根目录时用 `vault-dir: .`)。
4. **Commit changes**。
5. 启用 Pages:**Settings → Pages → Source: GitHub Actions**。
6. **Actions** 标签页 → “Publish site” workflow → **Run workflow**(运行工作流)。

约 2 分钟后,网站就在 `username.github.io/repository-name` 上线了。下一站——[[如何更新网站]]。

## 第 4 步——变成你自己的网站

在仓库根目录创建 `markdown-publish.config.json`:

```json
{
  "siteName": "我的笔记",
  "siteLang": "zh",
  "vaultDir": "vault",
  "buildMode": "full"
}
```

- `buildMode: "public"`——只发布 frontmatter 里带 `publish: public` 的笔记(其余内容不会出现在网站、搜索和关系图谱里)。
- 其余所有配置项见 [[配置]]。

> [!note] 想更简单?
> 还没有 vault,或者只想先随便看看——那就从[[几次点击搞定|几次点击的模板]]开始,之后再把笔记搬进去。
