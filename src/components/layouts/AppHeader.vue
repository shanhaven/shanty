<script setup lang="ts">
import { useDark } from '@vueuse/core'
import DarkLogo from '@/assets/defaults/logo-dark.png'
import LightLogo from '@/assets/defaults/logo-light.png'
import TopNavigation from '@/components/layouts/TopNavigation.vue'
import MobileDrawer from '@/components/layouts/MobileDrawer.vue'

const isDark = useDark()
</script>

<template>
  <header class="container flex items-center justify-between p-2 lg:px-8">
    <!-- Logo -->
    <div class="flex lg:flex-1">
      <RouterLink to="/" class="-m-1.5 p-1.5">
        <span class="sr-only">Shanty Cajulao</span>
        <img v-if="isDark" class="h-12 w-auto" :src="DarkLogo" alt="Shanty Cajulao Logo" />
        <img v-else class="h-12 w-auto" :src="LightLogo" alt="Shanty Cajulao Logo" />
      </RouterLink>
    </div>

    <!-- Mobile Drawer Button -->
    <MobileDrawer />

    <!-- Top Navigation -->
    <TopNavigation />
  </header>
</template>
