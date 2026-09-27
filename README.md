# Coding Concepts — C Edition

Nine modules tracing an arc from C's raw data types through memory, data organisation, dynamic allocation, the standard library, file I/O, modular multi-file projects, the build pipeline, and finally systems-level bit manipulation — the same foundation the Arduino edition builds on.

| # | Module |
|---|--------|
| 1 | C Data Types |
| 2 | Arrays & Pointers |
| 3 | Structs & Unions |
| 4 | Dynamic Memory |
| 5 | The C Standard Library |
| 6 | File I/O |
| 7 | Function Pointers & Modularity |
| 8 | The Preprocessor & Build Systems |
| 9 | Advanced C — Systems & Performance |

## Architecture

Same data-driven design as the other editions in this series: content lives in `data/*.json`, rendered by a shared `chapter.html` + `assets/app.js`.

```
index.html / chapter.html   — page shells
assets/styles.css           — shared styling
assets/app.js                — JSON-driven renderer, syntax highlighting, persistence
data/chapters.json           — nav/index summary
data/chapter1.json … 9       — full content per chapter
wrangler.toml / package.json — Cloudflare Pages config + npm scripts
```

Edit a chapter by editing its `data/chapterN.json` — no HTML/JS changes needed.

## Running locally

```bash
python3 -m http.server 8000   # fetch() needs http://, not file://
```

## Deploying

- **GitHub Pages** — push to GitHub, enable Pages on `main` / root (or drag-and-drop upload via GitHub's web UI, no git needed).
- **Cloudflare Pages (Git-connected)** — Workers & Pages → Create → Connect to Git → Build command empty, Output directory `/`.
- **Cloudflare Pages (Direct upload)** — Workers & Pages → Create → Upload assets → drag this folder in.
- **Cloudflare Pages (CLI)** — `npm install && npx wrangler login && npm run deploy`.

## Progress

Checklists and notes save to `localStorage` per chapter — nothing leaves the browser.

## Author

Kamol Das · Microbiology, University of Chittagong