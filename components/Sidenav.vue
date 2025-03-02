<script setup>
import { ref } from 'vue'

const navItems = ref([
  { name: 'Dashboard', icon: '🐶', link: '#' },
  { name: 'Projecten', icon: '🐱', link: '#' },
  { name: 'Berichten', icon: '🐭', link: '#' },
  { name: 'Eigen Projecten', icon: '🐹', link: '#' },
  { name: 'Notificaties', icon: '🐰', link: '#' },
  { name: 'To-do\'s', icon: '🦊', link: '#' },
  { name: 'Profiel', icon: '🐻', link: '#' }
])
</script>

<template>
  <div class="flex flex-col p-4 gap-16">
    <button class="self-end">
      X
    </button>
    <nav>
      <ul class="flex flex-col gap-4">
        <li v-for="item in navItems">
          <a :href="item.link">
            {{item.icon}}
            {{ item.name }}
          </a>
        </li>
      </ul>
    </nav>
  </div>
</template>
