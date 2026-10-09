<script setup>
import { ref } from 'vue'

// index.html set it before the first paint.
const theme = ref(document.documentElement.dataset.theme || 'dark')

function toggle() {
  theme.value = theme.value === 'dark' ? 'light' : 'dark'
  document.documentElement.dataset.theme = theme.value
  try {
    localStorage.setItem('theme', theme.value)
  } catch (e) {}
}
</script>

<template>
  <button class="toggle" :aria-label="theme === 'dark' ? 'Switch to light mode' : 'Switch to dark mode'" :title="theme === 'dark' ? 'Light mode' : 'Dark mode'" @click="toggle">
    <!-- Sun in dark mode (what you'd switch to), moon in light. -->
    <svg v-if="theme === 'dark'" viewBox="0 0 24 24" width="20" height="20" aria-hidden="true">
      <circle cx="12" cy="12" r="4.5" fill="currentColor" />
      <path d="M12 2v2.5M12 19.5V22M2 12h2.5M19.5 12H22M4.9 4.9l1.8 1.8M17.3 17.3l1.8 1.8M4.9 19.1l1.8-1.8M17.3 6.7l1.8-1.8" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
    </svg>
    <svg v-else viewBox="0 0 24 24" width="20" height="20" aria-hidden="true">
      <path d="M20 14.5A8.5 8.5 0 1 1 9.5 4a7 7 0 0 0 10.5 10.5z" fill="currentColor" />
    </svg>
  </button>
</template>

<style scoped>
.toggle {
  display: grid;
  place-items: center;
  width: 38px;
  height: 38px;
  border-radius: 999px;
  border: 1px solid var(--border);
  background: var(--surface);
  color: var(--text);
  cursor: pointer;
  transition: border-color 0.15s;
}
.toggle:hover {
  border-color: var(--accent);
  color: var(--accent-ink);
}
</style>
