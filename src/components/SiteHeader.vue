<script setup>
import { ref } from 'vue'
import ThemeToggle from './ThemeToggle.vue'

const open = ref(false)
const links = [
  { href: '#features', label: 'Features' },
  { href: '#components', label: 'Components' },
  { href: '#try', label: 'Try it' },
  { href: '#status', label: 'Roadmap' },
]
</script>

<template>
  <header class="bar">
    <div class="wrap row">
      <a href="#top" class="brand" aria-label="HeroineOS home">
        <svg viewBox="0 0 32 32" width="28" height="28" aria-hidden="true">
          <rect width="32" height="32" rx="7" class="mark-bg" />
          <path d="M9 7v18M23 7v18M9 16h14" stroke="var(--accent)" stroke-width="4" stroke-linecap="round" />
        </svg>
        <span>Heroine<b>OS</b></span>
      </a>
      <nav :class="{ open }" aria-label="Main">
        <a v-for="l in links" :key="l.href" :href="l.href" @click="open = false">{{ l.label }}</a>
        <a href="https://github.com/HeroineOS" rel="noopener">GitHub</a>
      </nav>
      <div class="end">
        <ThemeToggle />
        <button class="menu" :aria-expanded="open" aria-label="Menu" @click="open = !open">
          <svg viewBox="0 0 24 24" width="22" height="22" aria-hidden="true">
            <path :d="open ? 'M6 6l12 12M18 6L6 18' : 'M4 7h16M4 12h16M4 17h16'" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
          </svg>
        </button>
      </div>
    </div>
  </header>
</template>

<style scoped>
.bar {
  position: sticky;
  top: 0;
  z-index: 10;
  background: color-mix(in srgb, var(--bg) 85%, transparent);
  backdrop-filter: blur(10px);
  border-bottom: 1px solid var(--border);
}
.row {
  display: flex;
  align-items: center;
  gap: 24px;
  height: 60px;
}
.brand {
  display: flex;
  align-items: center;
  gap: 10px;
  color: var(--text);
  font-size: 1.15rem;
  font-weight: 500;
}
.brand:hover {
  text-decoration: none;
}
.brand b {
  color: var(--accent-ink);
}
.mark-bg {
  fill: #19171f;
}
nav {
  display: flex;
  gap: 22px;
  margin-left: auto;
}
nav a {
  color: var(--text-dim);
  font-weight: 500;
}
nav a:hover {
  color: var(--text);
  text-decoration: none;
}
.end {
  display: flex;
  align-items: center;
  gap: 6px;
}
.menu {
  display: none;
  background: none;
  border: 0;
  color: var(--text);
  padding: 6px;
  cursor: pointer;
}
@media (max-width: 760px) {
  .menu {
    display: block;
  }
  .end {
    margin-left: auto;
  }
  nav {
    display: none;
    position: absolute;
    top: 60px;
    left: 0;
    right: 0;
    flex-direction: column;
    gap: 0;
    background: var(--bg);
    border-bottom: 1px solid var(--border);
    padding: 8px 24px 16px;
  }
  nav.open {
    display: flex;
  }
  nav a {
    padding: 10px 0;
  }
}
</style>
