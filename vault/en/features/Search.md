# Search

Search runs **entirely in your browser** — no server, no queries sent anywhere. The index ([Pagefind](https://pagefind.app)) is built together with the site and loads in small chunks, so it stays fast even on large vaults.

## How to use it

- Click the "Search page or heading…" field in the sidebar — or press **Ctrl+K** (`Cmd+K` on Mac).
- Type your query — results appear as you type, with matches highlighted.
- Arrow keys ↑/↓ to select, **Enter** to open, **Esc** to close.

Try it right now: press `Ctrl+K` and type "configuration".

## Under the hood

During the build, every page gets indexed and the index is placed next to the static files. The browser only loads the fragments of the index it needs — so the first search takes milliseconds instead of downloading megabytes.

Notes hidden by `public` mode ([[Configuration]]) don't make it into the index.

Besides the human-facing search, the site also has a machine one — for AI agents: [[AI Agents (WebMCP)]].
