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

      <figure class="mascot">
        <img src="/heroine.webp" width="460" height="460" alt="Heroine, the HeroineOS mascot: a catgirl with long taupe hair in a black hoodie" />
      </figure>
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

/* Heroine, on her own background color (the dark surface). */
.mascot {
  margin: 0;
  justify-self: center;
  max-width: 420px;
  width: 100%;
}
.mascot img {
  display: block;
  width: 100%;
  height: auto;
  border-radius: 24px;
  border: 1px solid var(--border);
  box-shadow: 0 40px 80px -40px color-mix(in srgb, var(--accent) 45%, transparent);
}
@media (max-width: 900px) {
  .grid2 {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}
</style>
