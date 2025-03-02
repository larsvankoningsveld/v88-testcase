<script setup>
import { ref } from 'vue'
const collapsed = ref(false)

const navItems = ref([
  { name: 'Dashboard', icon: '🐶', link: '#' },
  { name: 'Projecten', icon: '🐱', link: '#' },
  { name: 'Berichten', icon: '🐭', link: '#' },
  { name: 'Eigen Projecten', icon: '🐹', link: '/' },
  { name: 'Notificaties', icon: '🐰', link: '#' },
  { name: 'To-do\'s', icon: '🦊', link: '#' },
  { name: 'Profiel', icon: '🐻', link: '#' }
])
</script>

<template>
  <div class="flex flex-col p-4 gap-16 bg-white h-full">
    <button @click="collapsed = !collapsed" class="self-end">
      <div v-if="collapsed">
        -> </div>
      <div v-else>
        <- </div>
    </button>
    <nav>
      <ul class="flex flex-col gap-8">
        <li v-for="item in navItems">
          <a :href="item.link">
            <div class="flex gap-4 px-2 py-1 hover:bg-blue-50 active:bg-blue-50 rounded-lg">
              <div>
                {{ item.icon }}
              </div>
              <div :class="{ hidden: collapsed }">
                {{ item.name }}
              </div>
            </div>
          </a>
        </li>
      </ul>
    </nav>
  </div>
</template>
