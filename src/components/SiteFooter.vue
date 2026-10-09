<script setup>
const year = new Date().getFullYear()
</script>

<template>
  <footer>
    <div class="wrap row">
      <div>
        <strong>Heroine<span>OS</span></strong>
        <p>Addicted to pure optimization.</p>
      </div>
      <nav aria-label="Footer">
        <a href="https://github.com/HeroineOS" rel="noopener">GitHub</a>
        <a href="https://github.com/HeroineOS/HeroWM" rel="noopener">HeroWM</a>
        <a href="https://github.com/HeroineOS/HeroUI" rel="noopener">HeroUI</a>
        <a href="https://www.debian.org" rel="noopener">Debian</a>
      </nav>
    </div>
    <div class="wrap fine">
      © {{ year }} HeroineOS contributors. Built on Debian; not affiliated with the Debian project.
    </div>
  </footer>
</template>

<style scoped>
footer {
  border-top: 1px solid var(--border);
  padding: 40px 0 28px;
  color: var(--text-dim);
  font-size: 0.92rem;
}
.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  gap: 24px;
}
strong {
  color: var(--text);
  font-size: 1.05rem;
}
strong span {
  color: var(--accent-ink);
}
p {
  margin: 4px 0 0;
}
nav {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
}
nav a {
  color: var(--text-dim);
}
nav a:hover {
  color: var(--text);
}
.fine {
  margin-top: 28px;
  font-size: 0.82rem;
}
</style>
