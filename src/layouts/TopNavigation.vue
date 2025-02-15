<script setup lang="ts">
import { useRoute } from 'vue-router'
import { navigation } from '@/layouts/composables/navigation.ts'

const route = useRoute()
</script>

<template>
  <nav class="hidden lg:flex lg:gap-x-12">
    <RouterLink
      v-for="item in navigation"
      :key="item.name"
      :to="item.path"
      class="text-sm font-semibold transition duration-200"
      :class="route.path === item.path ? 'text-teal-600 dark:text-teal-400' : 'text-gray-900 dark:text-gray-100 hover:text-teal-500 dark:hover:text-teal-300'"
    >
      {{ item.name }}
    </RouterLink>
  </nav>
</template>
