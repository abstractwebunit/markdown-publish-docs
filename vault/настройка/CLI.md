# CLI

Собрать сайт можно на любой машине с Node.js 20+ — одной командой, без установки:

```bash
npx @abstractwebunit/markdown-publish build --vault путь/к/заметкам --out dist
```

В `dist` появится готовый статический сайт — открой его любым статик-сервером или закинь на любой хостинг.

## Флаги

| Флаг | Что делает |
|---|---|
| `--vault <папка>` | Путь к vault (перекрывает всё) |
| `--vault-dir <папка>` | То же, но относительно текущей папки/конфига |
| `--out <папка>` | Куда собрать сайт (по умолчанию `dist`) |
| `--config <файл>` | Путь к конфигу (по умолчанию `markdown-publish.config.json`) |
| `--site-name`, `--site-url`, `--site-lang`, `--site-description`, `--site-footer` | См. [[Конфигурация]] |
| `--build-mode full\|public` | Публиковать всё или только `publish: public` |
| `--base-href </путь/>` | Под-путь сайта (для GitHub Pages — `/имя-репозитория/`) |

Флаги перекрывают конфиг-файл, так что можно держать общие настройки в `markdown-publish.config.json`, а отличия передавать флагами.

## Пример: собрать и посмотреть локально

```bash
npx @abstractwebunit/markdown-publish build --vault ./мои-заметки --out site
npx serve site
```

> [!note] Windows + Git Bash
> Git Bash может «съесть» значение `--base-href /sub/`, превратив его в путь Windows. Лечится префиксом `MSYS_NO_PATHCONV=1` перед командой. В обычных PowerShell/cmd и на CI такого нет.
