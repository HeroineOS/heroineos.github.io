<script setup>
import { ref } from 'vue'

const install = `mkdir -p ~/.local/bin
curl -fsSL https://raw.githubusercontent.com/HeroineOS/HeroUpdate/main/heroupdate -o ~/.local/bin/heroupdate
chmod +x ~/.local/bin/heroupdate
heroupdate`

const copied = ref(false)
async function copy() {
  try {
    await navigator.clipboard.writeText(install)
    copied.value = true
    setTimeout(() => (copied.value = false), 1600)
  } catch (e) {}
}
</script>

<template>
  <section id="try" class="alt">
    <div class="wrap grid2">
      <div>
        <p class="eyebrow">Try it</p>
        <h2>Run the desktop on Debian today.</h2>
        <p class="lead">There's no installer image yet. The desktop's components already run on Debian (testing or newer) on x86-64 and ARM64: one command fetches the latest of each and keeps them up to date.</p>
        <ul class="steps">
          <li>Asks before installing anything, and installs through apt.</li>
          <li>Run <code>heroupdate --check</code> to only see what's new.</li>
          <li>Later, a signed apt repository replaces it: <code>sudo apt upgrade</code> and done.</li>
        </ul>
      </div>
      <div class="term">
        <div class="term-head">
          <span>Terminal</span>
          <button class="copy" @click="copy">{{ copied ? 'Copied' : 'Copy' }}</button>
        </div>
        <pre><code><template v-for="(line, i) in install.split('\n')" :key="i"><span class="p">$ </span>{{ line }}
</template></code></pre>
      </div>
    </div>
  </section>
</template>

<style scoped>
.grid2 {
  display: grid;
  grid-template-columns: 1fr 1.1fr;
  gap: 48px;
  align-items: center;
}
.steps {
  padding-left: 1.2em;
  color: var(--text-dim);
}
.steps li {
  margin: 6px 0;
}
.steps code {
  color: var(--text);
}
.term {
  background: var(--code-bg);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  overflow: hidden;
  color: #ecebef;
}
.term-head {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 8px 12px 8px 16px;
  border-bottom: 1px solid #2c2935;
  font-size: 0.8rem;
  color: #a19ca9;
}
.copy {
  font: 600 0.8rem var(--font);
  padding: 4px 10px;
  border-radius: 6px;
  border: 1px solid #3a3644;
  background: #23212d;
  color: #ecebef;
  cursor: pointer;
}
.copy:hover {
  border-color: var(--accent);
}
pre {
  margin: 0;
  padding: 16px;
  line-height: 1.7;
  white-space: pre-wrap;
  overflow-wrap: anywhere;
}
.p {
  color: var(--accent);
  user-select: none;
}
@media (max-width: 900px) {
  .grid2 {
    grid-template-columns: 1fr;
  }
}
</style>
