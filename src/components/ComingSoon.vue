<script setup lang="ts">
import Dark from '../assets/defaults/coming-soon-dark.jpg'
import Light from '../assets/defaults/coming-soon-light.jpg'
import { useDark } from '@vueuse/core'

const isDark = useDark();
</script>

<template>
  <div
    class="container relative isolate top-0 left-0 w-full h-[calc(100dvh-64px)] bg-contain bg-no-repeat bg-top"
    :style="{ backgroundImage: `url(${isDark ? Dark : Light})` }"
  >
  </div>
</template>

<style scoped>
</style>
