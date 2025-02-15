<script setup lang="ts">
import { ref } from 'vue'
import { useRoute } from 'vue-router'
import { Dialog, DialogPanel } from '@headlessui/vue'
import { XMarkIcon, Bars3Icon } from '@heroicons/vue/24/outline'
import { navigation } from '@/components/layouts/composables/navigation.ts'

const mobileMenuOpen = ref(false)
const route = useRoute()
</script>

<template>
  <!-- Mobile Menu Button -->
  <div class="flex lg:hidden">
    <button type="button" class="-m-2.5 p-2.5 rounded-md text-gray-700 dark:text-gray-100" @click="mobileMenuOpen = true">
      <span class="sr-only">Open main menu</span>
      <Bars3Icon class="size-6" aria-hidden="true" />
    </button>
  </div>

  <!-- Mobile Drawer -->
  <Dialog class="lg:hidden" @close="mobileMenuOpen = false" :open="mobileMenuOpen">
    <div class="fixed inset-0 z-50" />
    <DialogPanel class="fixed inset-y-0 right-0 z-50 w-full sm:max-w-sm bg-white dark:bg-gray-800 px-6 py-6 border-l border-gray-600">
      <div class="flex items-center justify-between">
        <!-- Close Button -->
        <button type="button" class="-m-2.5 p-2.5 rounded-md text-gray-700 dark:text-gray-100" @click="mobileMenuOpen = false">
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
              class="-mx-3 block rounded-lg px-3 py-2 text-base font-semibold transition duration-200"
              :class="route.path === item.path ? 'bg-teal-600 text-white dark:bg-teal-500' : 'text-gray-900 dark:text-gray-100 hover:bg-gray-700'"
              @click="mobileMenuOpen = false"
            >
              {{ item.name }}
            </RouterLink>
          </div>
        </div>
      </div>
    </DialogPanel>
  </Dialog>
</template>
