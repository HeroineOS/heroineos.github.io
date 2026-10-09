<script setup>
import DesktopSketch from './DesktopSketch.vue'

const parts = [
  { name: 'HeroWM', repo: 'HeroWM', what: 'The Wayland compositor, from fht-compositor: tiling and floating windows, workspaces, animations.', state: 'In progress' },
  { name: 'HeroBar', repo: 'HeroBar', what: 'The panel: workspaces, taskbar with folders, clock, sound, network, battery.', state: 'Usable' },
  { name: 'HeroLauncher', repo: 'HeroLauncher', what: 'The app launcher: a menu or centered, favorites, categories, search.', state: 'Usable' },
  { name: 'HeroAppearance', repo: 'HeroAppearance', what: 'Themes, the panel\'s layout, the launcher and the wallpaper, all changed live.', state: 'Usable' },
  { name: 'HeroWallpaper', repo: 'HeroWallpaper', what: 'Pictures, animated pictures and looping videos, for next to no memory.', state: 'Usable' },
  { name: 'HeroPortal', repo: 'HeroPortal', what: 'The open and save dialogs every app gets, browsers included.', state: 'Usable' },
  { name: 'HeroUI', repo: 'HeroUI', what: 'The small Rust toolkit all of them are built with, on FLTK.', state: 'Library' },
  { name: 'HeroUpdate', repo: 'HeroUpdate', what: 'One command that installs and updates every component, until the apt repository is up.', state: 'Tool' },
]
</script>

<template>
  <section id="components">
    <div class="wrap">
      <div class="intro">
        <div>
          <p class="eyebrow">The desktop</p>
          <h2>Small programs, each doing one thing well.</h2>
          <p class="lead">Each part of the desktop is its own program and its own repository, so you can use all of it or just the pieces you want on another Wayland desktop.</p>
        </div>
        <DesktopSketch />
      </div>
      <div class="grid parts">
        <a v-for="p in parts" :key="p.name" class="card part" :href="`https://github.com/HeroineOS/${p.repo}`" rel="noopener">
          <div class="head">
            <h3>{{ p.name }}</h3>
            <span class="tag" :class="{ on: p.state === 'Usable' }">{{ p.state }}</span>
          </div>
          <p>{{ p.what }}</p>
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.intro {
  display: grid;
  grid-template-columns: 1fr 0.9fr;
  gap: 48px;
  align-items: center;
}
@media (max-width: 900px) {
  .intro {
    grid-template-columns: 1fr;
  }
}
.parts {
  margin-top: 36px;
}
.part {
  color: inherit;
  transition: border-color 0.15s, transform 0.15s;
}
.part:hover {
  text-decoration: none;
  border-color: var(--accent);
  transform: translateY(-2px);
}
.head {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: 8px;
  margin-bottom: 6px;
}
.head h3 {
  margin: 0;
}
</style>
