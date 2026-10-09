<script setup>
const roadmap = [
  { done: true, text: 'Panel, launcher, settings, wallpaper and file dialogs' },
  { done: true, text: 'Themes, with live changes everywhere' },
  { done: false, text: 'Notifications, with history and do-not-disturb' },
  { done: false, text: 'Window title bars drawn by the desktop' },
  { done: false, text: 'Signed apt repository: main (HeroineOS) and extra' },
  { done: false, text: 'Installer image' },
]
</script>

<template>
  <section id="status">
    <div class="wrap grid2">
      <div>
        <p class="eyebrow">Roadmap</p>
        <h2>Where it's at.</h2>
        <p class="lead">HeroineOS is young and moves fast. Components are released as testing builds while the pieces come together.</p>
        <a class="btn" href="https://github.com/orgs/HeroineOS/repositories" rel="noopener">All repositories</a>
      </div>
      <ol class="road">
        <li v-for="r in roadmap" :key="r.text" :class="{ done: r.done }">
          <span class="dot" aria-hidden="true">
            <svg v-if="r.done" viewBox="0 0 16 16" width="12" height="12"><path d="M3 8.5l3 3 7-7" fill="none" stroke="currentColor" stroke-width="2.4" stroke-linecap="round" stroke-linejoin="round" /></svg>
          </span>
          <span>{{ r.text }}</span>
          <span class="visually-hidden">{{ r.done ? '(done)' : '(planned)' }}</span>
        </li>
      </ol>
    </div>
  </section>
</template>

<style scoped>
.grid2 {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 48px;
  align-items: start;
}
.road {
  list-style: none;
  margin: 0;
  padding: 0;
}
.road li {
  display: flex;
  align-items: center;
  gap: 14px;
  padding: 14px 0;
  border-bottom: 1px solid var(--border);
  color: var(--text-dim);
}
.road li.done {
  color: var(--text);
}
.dot {
  flex: none;
  display: grid;
  place-items: center;
  width: 22px;
  height: 22px;
  border-radius: 99px;
  border: 2px solid var(--border);
}
.done .dot {
  background: var(--accent);
  border-color: var(--accent);
  color: var(--on-accent);
}
.visually-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  overflow: hidden;
  clip: rect(0 0 0 0);
}
@media (max-width: 900px) {
  .grid2 {
    grid-template-columns: 1fr;
  }
}
</style>
