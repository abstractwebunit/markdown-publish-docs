# Vercel

Сайт живёт на `имя.vercel.app` (бесплатный тариф Hobby).

## Кнопкой

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/abstractwebunit/markdown-publish-template&project-name=my-notes&repository-name=my-notes)

Vercel создаст копию [[За пару кликов|шаблона]] в твоём GitHub и соберёт сайт. Заметки — в папке `vault/`.

## Свой репозиторий

1. Положи в корень репозитория файл `vercel.json`:

```json
{
  "buildCommand": "npx --yes @abstractwebunit/markdown-publish build --out dist",
  "outputDirectory": "dist"
}
```

2. На [vercel.com/new](https://vercel.com/new) импортируй свой репозиторий → **Deploy**.

При каждом push сайт пересобирается.

> [!tip] base-href не нужен
> Как и на [[Netlify]], сайт живёт в корне домена — `base-href` по умолчанию (`/`) подходит.

Настройки сайта: [[Конфигурация]].
