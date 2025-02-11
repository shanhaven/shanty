<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import DarkModeToggle from '@/components/layouts/DarkModeToggle.vue'
</script>

<template>
  <header class="bg-gray-100 dark:bg-gray-800 dark:text-white text-center py-2 border-b border-gray-200 dark:border-gray-800">
    <nav>
      <RouterLink
        activeClass="text-teal-500"
        exactActiveClass="text-teal-600"
        to="/">Home</RouterLink> |
      <RouterLink
        activeClass="text-teal-500"
        exactActiveClass="text-teal-600"
        to="/about">About</RouterLink>  |
      <RouterLink
        activeClass="text-teal-500"
        exactActiveClass="text-teal-600"
        to="/projects">Projects</RouterLink> |
      <RouterLink
        activeClass="text-teal-500"
        exactActiveClass="text-teal-600"
        to="/blogs">Blogs</RouterLink> |
      <RouterLink
        activeClass="text-teal-500"
        exactActiveClass="text-teal-600"
        to="/contact">Contact</RouterLink>
    </nav>
  </header>
  <main class="dark:bg-gray-900 min-h-vh min-h-screen">
    <RouterView />
  </main>
  <DarkModeToggle/>
</template>

<style scoped>

</style>
