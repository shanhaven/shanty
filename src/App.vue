<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import DarkModeToggle from '@/components/layouts/DarkModeToggle.vue'
</script>

<template>
  <header class="bg-white dark:bg-gray-800">
    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
    </nav>
  </header>
  <main class="bg-white dark:bg-gray-900 min-h-vh min-h-screen">
    <RouterView />
  </main>
  <DarkModeToggle/>
</template>

<style scoped>
</style>
