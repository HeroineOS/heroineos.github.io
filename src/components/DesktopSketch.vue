<template>
  <div class="screen" role="img" aria-label="A sketch of the HeroineOS desktop: the bar on top and tiled windows">
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
</template>

<style scoped>
/* Always dark, like the real default. */
.screen {
  --s-bg: #131119;
  --s-panel: #23212d;
  --s-win: #1e1c25;
  --s-line: #36323f;
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
  color: #dcdae0;
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
  background: #4a4654;
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
  background: #4a4654;
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
  background: #3d3946;
}
.term {
  padding: 10px 12px;
  font: 12px/1.7 var(--mono);
  color: #ecebef;
}
.term p {
  margin: 0;
}
.term b {
  color: var(--accent);
}
.term .dim {
  color: #8f8a97;
}
.caret {
  display: inline-block;
  width: 7px;
  height: 13px;
  vertical-align: -2px;
  background: #ecebef;
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
@media (prefers-reduced-motion: reduce) {
  .caret {
    animation: none;
  }
}
</style>
