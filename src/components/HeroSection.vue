<template>
  <section id="top" class="hero">
    <div class="wrap grid2">
      <div>
        <p class="eyebrow">Debian-based · Wayland · In development</p>
        <h1>Addicted to <span class="hl">pure optimization</span>.</h1>
        <p class="lead">
          HeroineOS is a fast, light Linux distribution with a desktop of its own: every piece built
          to use as little memory and CPU as it can, and measured to prove it. From old laptops to ARM
          Chromebooks.
        </p>
        <div class="ctas">
          <a class="btn primary" href="#try">Try the desktop</a>
          <a class="btn" href="https://github.com/HeroineOS" rel="noopener">
            <svg viewBox="0 0 16 16" width="18" height="18" aria-hidden="true"><path fill="currentColor" d="M8 0a8 8 0 0 0-2.53 15.59c.4.07.55-.17.55-.38v-1.33c-2.23.48-2.7-1.07-2.7-1.07-.36-.92-.89-1.17-.89-1.17-.73-.5.06-.49.06-.49.8.06 1.23.83 1.23.83.71 1.23 1.88.87 2.34.67.07-.52.28-.87.5-1.07-1.78-.2-3.65-.89-3.65-3.95 0-.87.31-1.59.83-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82a7.6 7.6 0 0 1 4 0c1.53-1.03 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.28.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48v2.2c0 .21.15.46.55.38A8 8 0 0 0 8 0z"/></svg>
            Source on GitHub
          </a>
        </div>
        <p class="note">No ISO yet: the desktop's parts run on Debian today.</p>
      </div>

      <!-- A small sketch of the desktop: bar, tiled windows, launcher. -->
      <div class="screen" aria-hidden="true">
        <div class="topbar">
          <span class="cat"></span>
          <span class="ws"><i class="on"></i><i></i><i></i><i></i></span>
          <span class="clock">09:41</span>
          <span class="sys"><i></i><i></i><i></i></span>
        </div>
        <div class="tiles">
          <div class="win big">
            <div class="title"><i></i><i></i><i></i></div>
            <div class="term">
              <p><b>$</b> herowallpaper --version</p>
              <p class="dim">herowallpaper 0.1.7</p>
              <p><b>$</b> herobar --version</p>
              <p class="dim">herobar 0.1.20</p>
              <p><b>$</b> <span class="caret"></span></p>
            </div>
          </div>
          <div class="col">
            <div class="win"><div class="title"><i></i><i></i><i></i></div><div class="lines"><i></i><i></i><i class="s"></i></div></div>
            <div class="win"><div class="title"><i></i><i></i><i></i></div><div class="lines"><i class="s"></i><i></i></div></div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  padding: 72px 0 88px;
  background:
    radial-gradient(900px 400px at 85% 0%, color-mix(in srgb, var(--accent) 12%, transparent), transparent 70%),
    var(--bg);
}
.grid2 {
  display: grid;
  grid-template-columns: 1.05fr 1fr;
  gap: 56px;
  align-items: center;
}
h1 {
  font-size: clamp(2.4rem, 5.4vw, 3.8rem);
  font-weight: 800;
  letter-spacing: -0.03em;
  margin-bottom: 0.4em;
}
.hl {
  color: var(--accent-ink);
}
.ctas {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin: 28px 0 14px;
}
.note {
  color: var(--text-dim);
  font-size: 0.9rem;
}

/* The desktop sketch: always dark, like the real default. */
.screen {
  --s-bg: #0f0f0f;
  --s-panel: #1b1b1b;
  --s-win: #191919;
  --s-line: #2e2e2e;
  background: var(--s-bg);
  border: 1px solid var(--border);
  border-radius: 14px;
  padding: 10px;
  aspect-ratio: 16 / 10.5;
  display: flex;
  flex-direction: column;
  gap: 10px;
  box-shadow: 0 30px 60px -30px rgb(0 0 0 / 0.5);
}
.topbar {
  display: flex;
  align-items: center;
  gap: 10px;
  height: 26px;
  padding: 0 10px;
  background: var(--s-panel);
  border-radius: 8px;
  font: 600 11px var(--font);
  color: #d8d8d8;
}
.cat {
  width: 12px;
  height: 12px;
  border-radius: 3px;
  background: var(--accent);
}
.ws {
  display: flex;
  gap: 5px;
}
.ws i {
  width: 7px;
  height: 7px;
  border-radius: 99px;
  background: #4a4a4a;
}
.ws i.on {
  width: 18px;
  background: var(--accent);
}
.clock {
  margin: 0 auto;
}
.sys {
  display: flex;
  gap: 5px;
}
.sys i {
  width: 14px;
  height: 7px;
  border-radius: 3px;
  background: #4a4a4a;
}
.tiles {
  flex: 1;
  display: grid;
  grid-template-columns: 1.4fr 1fr;
  gap: 10px;
  min-height: 0;
}
.col {
  display: grid;
  gap: 10px;
}
.win {
  background: var(--s-win);
  border: 1px solid var(--s-line);
  border-radius: 8px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
}
.win.big {
  border-color: color-mix(in srgb, var(--accent) 70%, transparent);
}
.title {
  display: flex;
  gap: 5px;
  padding: 7px 9px;
  border-bottom: 1px solid var(--s-line);
}
.title i {
  width: 7px;
  height: 7px;
  border-radius: 99px;
  background: #3a3a3a;
}
.term {
  padding: 10px 12px;
  font: 12px/1.7 var(--mono);
  color: #e6e6e6;
}
.term p {
  margin: 0;
}
.term b {
  color: var(--accent);
}
.term .dim {
  color: #8c8c8c;
}
.caret {
  display: inline-block;
  width: 7px;
  height: 13px;
  vertical-align: -2px;
  background: #e6e6e6;
  animation: blink 1.1s steps(1) infinite;
}
@keyframes blink {
  50% {
    opacity: 0;
  }
}
.lines {
  padding: 12px;
  display: grid;
  gap: 8px;
}
.lines i {
  height: 7px;
  border-radius: 4px;
  background: var(--s-line);
}
.lines i.s {
  width: 60%;
}

@media (max-width: 900px) {
  .grid2 {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}
@media (prefers-reduced-motion: reduce) {
  .caret {
    animation: none;
  }
}
</style>
