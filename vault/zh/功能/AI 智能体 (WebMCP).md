# AI 智能体 (WebMCP)

网站不仅能把笔记展示给人,还能以结构化的方式提供给 AI 智能体——不需要费劲去抠 HTML。

## 这是什么

[WebMCP](https://github.com/webmachinelearning/webmcp) 是一个新兴的 Web 标准(W3C draft):页面在 `navigator.modelContext` 中注册“工具”,浏览器里的 AI 智能体就可以调用它们。markdown-publish 注册了四个:

| 工具 | 作用 |
|---|---|
| `search_notes(query, limit)` | 搜索笔记:标题、链接、摘要片段 |
| `get_note(slug)` | 笔记的**完整 markdown** + 反向链接 |
| `list_notes()` | 网站所有页面的列表 |
| `get_backlinks(slug)` | 谁链接了这篇笔记 |

如果浏览器没有原生的 `navigator.modelContext`,网站会安装自带的轻量 polyfill——没有第三方依赖。

## 亲手试试

打开 DevTools(F12)→ Console:

```js
await navigator.modelContext.callTool({
  name: 'search_notes',
  arguments: { query: '配置', limit: 3 },
})
```

## 还有给爬虫的

- `/llms.txt`——给 AI 爬虫的网站地图([llmstxt.org](https://llmstxt.org))。
- 每个页面都预渲染成干净的 HTML——不需要 JavaScript 也能读。
- `sitemap.xml`、`robots.txt`、OG 卡片和 JSON-LD——常规 SEO 同样齐全。

隐藏的笔记(`buildMode: public`,见 [[配置]])不会提供给智能体——它们根本不在构建产物里。
