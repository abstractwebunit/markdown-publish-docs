# Cloudflare Pages

Очень быстрый CDN, щедрый бесплатный тариф. Кнопки-в-один-клик у Cloudflare для такого типа проектов нет, но подключение занимает пару минут.

## Шаги

1. Залей заметки в GitHub-репозиторий (проще всего — из [[За пару кликов|шаблона]]).
2. В [дашборде Cloudflare](https://dash.cloudflare.com): **Workers & Pages → Create → Pages → Connect to Git** → выбери репозиторий.
3. В настройках сборки укажи:
   - **Build command:** `npx --yes @abstractwebunit/markdown-publish build --out dist`
   - **Build output directory:** `dist`
4. **Save and Deploy**. Сайт получит адрес `имя.pages.dev`.

При каждом push в репозиторий Cloudflare пересобирает сайт.

> [!tip] base-href не нужен
> Сайт живёт в корне `*.pages.dev`, так что `base-href` по умолчанию (`/`) подходит — в отличие от [[GitHub Pages]].

Название сайта, язык, описание — через `markdown-publish.config.json` в корне репозитория: [[Конфигурация]].
