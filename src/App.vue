<script setup>
import SiteHeader from './components/SiteHeader.vue'
import HeroSection from './components/HeroSection.vue'
import Features from './components/Features.vue'
import Components from './components/Components.vue'
import TryIt from './components/TryIt.vue'
import Status from './components/Status.vue'
import SiteFooter from './components/SiteFooter.vue'
</script>

<template>
  <SiteHeader />
  <main>
    <HeroSection />
    <Features />
    <Components />
    <TryIt />
    <Status />
  </main>
  <SiteFooter />
</template>
