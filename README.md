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

Colors come from the mascot (the org picture): her hair's pale muted taupe `#baada1` is
the accent, and the violet near-black behind her the dark theme.
They're variables at the top of `src/style.css`; `--accent-ink` is a deeper taupe for
text in light mode, where the pale one can't be read on white.
