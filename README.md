# heroineos.github.io

The HeroineOS website: one page, Vue 3 + Vite, no UI library, no web fonts, no images
(the desktop picture is drawn in HTML/CSS), about 33 KB gzipped in all. Light and dark
modes follow the system until a mode is picked with the toggle (kept in localStorage,
applied before the first paint).

```sh
npm install
npm run dev      # http://localhost:5173
npm run build    # dist/
```

Pushing to `main` builds and publishes it to GitHub Pages (`.github/workflows/pages.yml`).

The accent color is one variable at the top of `src/style.css`: `--accent`, plus
`--accent-ink` (a darker shade for text in light mode, where yellow is unreadable on white).
