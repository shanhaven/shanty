<script setup lang="ts">
import { useDark, useToggle } from '@vueuse/core';
import { SunIcon, MoonIcon } from '@heroicons/vue/24/outline'; // Or your preferred icon library
import { computed } from 'vue';

const isDark = useDark();
const toggleDark = useToggle(isDark);

const currentIcon = computed(() => isDark.value ? MoonIcon : SunIcon);

</script>

<template>
  <div class="dark-mode-toggle">
    <button @click="toggleDark()" class="toggle-button">
      <component :is="currentIcon" class="toggle-icon" />
    </button>
  </div>
</template>

<style scoped>
.dark-mode-toggle {
  position: fixed;
  bottom: 20px;
  right: 20px;
  z-index: 1000;
}

.toggle-button {
  background-color: transparent;
  border-radius: 50%;
  padding: 6px;
  cursor: pointer;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
  transition: background-color 0.3s ease;
}

.toggle-button:hover {
  background-color: rgba(0, 0, 0, 0.1);
  transform: scale(1.25);
}

.toggle-icon {
  width: 1rem;
  height: 1rem;
  color: #333;
  transition: color 0.3s ease;
}

.dark .toggle-button {
  border-radius: 50%;
  box-shadow: 0 3px 6px rgba(255, 255, 255, 0.2);
}
.dark .toggle-icon {
  color: #eee;
}
.dark .toggle-button:hover {
  background-color: rgba(0, 0, 0, 0.7);
  border: 1px solid rgba(30, 42, 58, 1);
}
</style>
