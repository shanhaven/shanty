<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import DarkModeToggle from '@/components/layouts/DarkModeToggle.vue'
import TopNavigation from '@/components/layouts/TopNavigation.vue'
</script>

<template>
  <header class="inset-x-0 top-0 z-50">
    <TopNavigation/>
  </header>
  <main class="dark:bg-gray-900 bg-white">
    <RouterView />
  </main>
  <DarkModeToggle/>
</template>

<style scoped>

</style>
