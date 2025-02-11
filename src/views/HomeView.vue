<script setup lang="ts">
import {useDark, useToggle} from '@vueuse/core'

const isDark = useDark()
const toggleDark = useToggle(isDark)
</script>

<template>
  <main class="bg-white dark:bg-gray-800">
    <h1>This is home page</h1>

    <p>isDark: {{isDark}}</p>
    <button class="px-4 py-2 text-white bg-teal-400 rounded-full" @click="toggleDark()" type="button">
      Toggle Dark Mode Here
    </button>
  </main>
</template>
