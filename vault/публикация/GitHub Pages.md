# GitHub Pages

Бесплатный хостинг от GitHub. Сайт живёт на `твой-ник.github.io/имя-репозитория`.

## Через шаблон (рекомендуется)

1. Открой [шаблон](https://github.com/abstractwebunit/markdown-publish-template/generate), придумай имя репозиторию, жми **Create repository**.
2. В новом репозитории: **Settings → Pages → Source** → выбери **GitHub Actions**.
3. Вкладка **Actions** → workflow «Publish site» → **Run workflow**.
4. Через ~2 минуты сайт доступен по адресу `твой-ник.github.io/имя-репозитория`.

Дальше: правишь заметки в `vault/` (хоть прямо на GitHub, хоть через git) — сайт пересобирается сам.

## Вручную в свой репозиторий

Если заметки уже лежат в твоём репозитории, добавь файл `.github/workflows/publish.yml`:

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
          site-url: https://ТВОЙ-НИК.github.io/РЕПОЗИТОРИЙ
          base-href: /РЕПОЗИТОРИЙ/
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

Замени `ТВОЙ-НИК` и `РЕПОЗИТОРИЙ`, включи Pages (Settings → Pages → Source: **GitHub Actions**) — готово.

> [!warning] Самая частая ошибка — `base-href`
> Сайт на GitHub Pages живёт на под-пути `/имя-репозитория/`. Если не указать `base-href: /имя-репозитория/`, страницы откроются, но стили и заметки отдадут 404. Подробнее: [[FAQ]].

Если vault лежит в подпапке — добавь `vault-dir: имя-папки` в блок `with:`. Все параметры: [[Конфигурация]].
