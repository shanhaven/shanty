<script setup lang="ts">
import { ref } from 'vue'
import { useRoute } from 'vue-router'
import { Dialog, DialogPanel } from '@headlessui/vue'
import { Bars3Icon, XMarkIcon } from '@heroicons/vue/24/outline'
import DarkLogo from '@/assets/defaults/logo-dark.png'
import LightLogo from '@/assets/defaults/logo-light.png'
import { useDark } from '@vueuse/core'

const navigation = [
  { name: 'Me', path: '/' },
  { name: 'Projects', path: '/projects' },
  { name: 'Blogs', path: '/blogs' },
]

const route = useRoute() // Get the current route
const mobileMenuOpen = ref(false)
const isDark = useDark()
</script>

<template>
  <nav class="container flex items-center justify-between p-2 lg:px-8" aria-label="Global">
    <div class="flex lg:flex-1">
      <RouterLink to="/" class="-m-1.5 p-1.5">
        <span class="sr-only">Shanty Cajulao</span>
        <img v-if="isDark" class="h-12 w-auto" :src="DarkLogo" alt="Shanty Cajulao Logo" />
        <img v-else class="h-12 w-auto" :src="LightLogo" alt="Shanty Cajulao Logo" />
      </RouterLink>
    </div>
    <div class="flex lg:hidden">
      <button type="button" class="-m-2.5 inline-flex items-center justify-center rounded-md p-2.5 text-gray-700 dark:text-gray-100" @click="mobileMenuOpen = true">
        <span class="sr-only">Open main menu</span>
        <Bars3Icon class="size-6" aria-hidden="true" />
      </button>
    </div>
    <div class="hidden lg:flex lg:gap-x-12">
      <RouterLink
        v-for="item in navigation"
        :key="item.name"
        :to="item.path"
        class="text-sm/6 font-semibold transition duration-200"
        :class="route.path === item.path ? 'text-teal-600 dark:text-teal-400' : 'text-gray-900 dark:text-gray-100 hover:text-teal-500 dark:hover:text-teal-300'"
      >
        {{ item.name }}
      </RouterLink>
    </div>
  </nav>

  <!-- Mobile Navigation -->
  <Dialog class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
    <div class="fixed inset-0 z-50" />
    <DialogPanel class="fixed inset-y-0 right-0 z-50 w-full overflow-y-auto bg-white dark:bg-gray-800 px-6 py-6 sm:max-w-sm sm:ring-1 sm:ring-gray-900/10 border-l border-gray-600">
      <div class="flex items-center justify-between">
        <RouterLink to="/" class="-m-1.5 p-1.5">
          <span class="sr-only">Shanty Cajulao</span>
          <img v-if="isDark" class="h-12 w-auto" :src="DarkLogo" alt="Shanty Cajulao Logo" />
          <img v-else class="h-12 w-auto" :src="LightLogo" alt="Shanty Cajulao Logo" />
        </RouterLink>
        <button type="button" class="-m-2.5 rounded-md p-2.5 text-gray-700 dark:text-gray-100" @click="mobileMenuOpen = false">
          <span class="sr-only">Close menu</span>
          <XMarkIcon class="size-6" aria-hidden="true" />
        </button>
      </div>
      <div class="mt-6 flow-root">
        <div class="-my-6 divide-y divide-gray-100/10">
          <div class="space-y-2 py-6">
            <RouterLink
              v-for="item in navigation"
              :key="item.name"
              :to="item.path"
              class="-mx-3 block rounded-lg px-3 py-2 text-base/7 font-semibold transition duration-200"
              :class="route.path === item.path ? 'bg-teal-600 text-white dark:bg-teal-500' : 'text-gray-900 dark:text-gray-100 hover:bg-gray-700'"
            >
              {{ item.name }}
            </RouterLink>
          </div>
        </div>
      </div>
    </DialogPanel>
  </Dialog>
</template>
