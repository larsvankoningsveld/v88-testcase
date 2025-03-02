<script setup>
import { ref } from 'vue'

const navItems = ref([
  'Dashboard',
  'Projecten',
  'Berichten',
  'Eigen Projecten',
  'Notificaties',
  'To-do\'s',
  'Profiel'
])
</script>

<template>
  <div>
    <button>
      X
    </button>
    <nav>
      <ul>
        <li v-for="item in navItems">
          <a href="">
            {{ item }}
          </a>
        </li>
      </ul>
    </nav>
  </div>
</template>
