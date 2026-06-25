<script setup lang="ts">
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
</script>

<template>
  <div class="portfolio">
    <NavBar />
    <main>
      <HeroSection />
      <ExperienceSection />
    </main>
  </div>
</template>

<style scoped>
.portfolio {
  width: 100%;
  min-height: 100vh;
  background: var(--bg);
}
</style>
