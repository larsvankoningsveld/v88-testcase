<script setup>
import { ref } from 'vue'
import dashboard from 'assets/svg/dashboard.svg'
import projects from 'assets/svg/projects.svg'
import messages from 'assets/svg/messages.svg'
import ownProjects from 'assets/svg/own-projects.svg'
import notifications from 'assets/svg/notifications.svg'
import todos from 'assets/svg/todos.svg'
import profile from 'assets/svg/profile.svg'

const collapsed = ref(false)

const navItems = ref([
  { name: 'Dashboard', icon: dashboard, link: '#' }, { name: 'Projecten', icon: projects, link: '#' },
  { name: 'Berichten', icon: messages, link: '#' },
  { name: 'Eigen Projecten', icon: ownProjects, link: '/' },
  { name: 'Notificaties', icon: notifications, link: '#' },
  { name: 'To-do\'s', icon: todos, link: '#' },
  { name: 'Profiel', icon: profile, link: '#' }
])
</script>

<template>
  <div class="flex flex-col p-4 gap-16 bg-white h-full">
    <button @click="collapsed = !collapsed" class="self-end">
      <div v-if="collapsed">
        <img src="assets/svg/unfold.svg" alt="">
      </div>
      <div v-else>
        <img src="assets/svg/collapse.svg" alt="">
      </div>
    </button>
    <nav>
      <ul class="flex flex-col gap-8">
        <li v-for="item in navItems">
          <a :href="item.link">
            <div class="flex gap-4 px-2 py-1 hover:bg-blue-50 active:bg-blue-50 rounded-lg">
              <img :src="item.icon" alt="#" class="h-4 w-4">
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
