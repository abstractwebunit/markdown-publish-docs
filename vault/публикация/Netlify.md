# Netlify

Сайт живёт на `имя.netlify.app` (бесплатный тариф). Главный плюс — кнопка, после которой делать вообще ничего не нужно.

## Кнопкой

[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/abstractwebunit/markdown-publish-template)

Netlify создаст копию [[За пару кликов|шаблона]] в твоём GitHub и сразу соберёт сайт. Заметки — в папке `vault/`.

## Свой репозиторий

1. Положи в корень репозитория файл `netlify.toml`:

```toml
[build]
  command = "npx --yes @abstractwebunit/markdown-publish build --out dist"
  publish = "dist"
```

2. На [app.netlify.com](https://app.netlify.com): **Add new site → Import an existing project** → выбери свой репозиторий → **Deploy**.

Netlify сам подхватит команду из `netlify.toml`. При каждом push сайт пересобирается.

> [!tip] base-href не нужен
> На Netlify сайт живёт в корне домена, так что `base-href` оставляй по умолчанию (`/`) — в отличие от [[GitHub Pages]].

Название сайта, язык и прочее — через `markdown-publish.config.json` рядом с `netlify.toml`: [[Конфигурация]].
