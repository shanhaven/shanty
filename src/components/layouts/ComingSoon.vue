<script setup lang="ts">
import Dark from '../../assets/defaults/coming-soon-dark.jpg'
import Light from '../../assets/defaults/coming-soon-light.jpg'
import { useDark } from '@vueuse/core'

const isDark = useDark();
</script>

<template>
  <div style="margin-top:-41px"
    class="container top-0 left-0 w-full h-screen bg-contain bg-no-repeat bg-top"
    :style="{ backgroundImage: `url(${isDark ? Dark : Light})` }"
  >
  </div>
</template>

<style scoped>
</style>
