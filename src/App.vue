<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import DarkModeToggle from '@/layouts/DarkModeToggle.vue'
import Footer from '@/layouts/AppFooter.vue'
import AppHeader from '@/layouts/AppHeader.vue'
</script>

<template>
  <header class="inset-x-0 top-0 z-50">
    <AppHeader />
  </header>
  <main class="dark:bg-gray-900 bg-white">
    <RouterView />
  </main>
  <DarkModeToggle/>
  <footer class="py-8">
    <Footer/>
  </footer>
</template>

<style scoped>

</style>
