<script setup>
// Measured numbers only (private memory of each running program).
const stats = [
  { value: '2.7 MB', label: 'HeroBar, the panel' },
  { value: '0.3 MB', label: 'HeroWallpaper, showing a picture' },
  { value: '0 MB', label: 'HeroLauncher while closed' },
  { value: '≤ 500 MB', label: 'Goal: whole desktop + a browser tab' },
]

const features = [
  {
    title: 'Light by measurement',
    text: 'Every component is measured for memory, CPU and wakeups before it ships. Programs that aren\'t on screen don\'t sit in memory: they start when you need them and exit after.',
    icon: 'M4 18h4v-6H4zm6 0h4V6h-4zm6 0h4v-9h-4z',
  },
  {
    title: 'Its own Wayland desktop',
    text: 'HeroWM, a tiling and floating compositor, with a panel, launcher, wallpaper and settings written for it in Rust: one consistent look, themed in one place.',
    icon: 'M3 5h18v11H3zM8 20h8M12 16v4',
  },
  {
    title: 'Keyboard and mouse alike',
    text: 'Everything works with either. Keyboard navigation follows the compositor\'s keybindings, and every key is yours to change.',
    icon: 'M3 7h18v10H3zM7 11h.01M11 11h.01M15 11h.01M8 14h8',
  },
  {
    title: 'Plain Debian underneath',
    text: 'apt, Debian\'s packages and Debian\'s security updates. HeroineOS adds its own packages on top without replacing what you know.',
    icon: 'M12 3l8 4v6c0 4-3.5 7-8 8-4.5-1-8-4-8-8V7z',
  },
  {
    title: 'For the hardware you have',
    text: 'Built and tested on x86-64 and ARM64, from old laptops to ARM Chromebooks, with 32-bit x86 and ARM kept in mind.',
    icon: 'M7 7h10v10H7zM9 3v4M15 3v4M9 17v4M15 17v4M3 9h4M3 15h4M17 9h4M17 15h4',
  },
  {
    title: 'Open source',
    text: 'Every component lives on GitHub under open licenses. Read it, build it, change it.',
    icon: 'M8 8l-4 4 4 4M16 8l4 4-4 4M14 5l-4 14',
  },
]
</script>

<template>
  <section id="features" class="alt">
    <div class="wrap">
      <div class="stats">
        <div v-for="s in stats" :key="s.label" class="stat">
          <strong>{{ s.value }}</strong>
          <span>{{ s.label }}</span>
        </div>
      </div>

      <p class="eyebrow">Why HeroineOS</p>
      <h2>Fast because it does less, not because it hides it.</h2>
      <p class="lead">A full desktop that stays out of your machine's way, so your memory and CPU go to the things you actually run.</p>

      <div class="grid features">
        <div v-for="f in features" :key="f.title" class="card">
          <svg viewBox="0 0 24 24" width="26" height="26" aria-hidden="true">
            <path :d="f.icon" fill="none" stroke="var(--accent-ink)" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" />
          </svg>
          <h3>{{ f.title }}</h3>
          <p>{{ f.text }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.stats {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 1px;
  background: var(--border);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  overflow: hidden;
  margin-bottom: 72px;
}
.stat {
  background: var(--surface);
  padding: 22px;
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.stat strong {
  font-size: 1.8rem;
  font-weight: 800;
  letter-spacing: -0.02em;
  color: var(--accent-ink);
}
.stat span {
  color: var(--text-dim);
  font-size: 0.9rem;
}
.features {
  margin-top: 36px;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
}
.card svg {
  margin-bottom: 10px;
}
@media (max-width: 760px) {
  .stats {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
