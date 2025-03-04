<script setup>
import { ref } from "vue";
import dashboard from "assets/svg/dashboard.svg";
import projects from "assets/svg/projects.svg";
import messages from "assets/svg/messages.svg";
import ownProjects from "assets/svg/own-projects.svg";
import notifications from "assets/svg/notifications.svg";
import todos from "assets/svg/todos.svg";
import profile from "assets/svg/profile.svg";

const collapsed = ref(false);

const navItems = ref([
  { name: "Dashboard", icon: dashboard, link: "#" },
  { name: "Projecten", icon: projects, link: "#" },
  { name: "Berichten", icon: messages, link: "#" },
  { name: "Eigen Projecten", icon: ownProjects, link: "/" },
  { name: "Notificaties", icon: notifications, link: "#" },
  { name: "To-do's", icon: todos, link: "#" },
  { name: "Profiel", icon: profile, link: "#" },
]);
</script>

<template>
  <div class="flex flex-col p-5 gap-20 bg-white h-full">
    <button
      @click="collapsed = !collapsed"
      class="self-end hover:cursor-pointer hover:bg-blue-50 active:bg-blue-50 rounded p-2"
    >
      <div v-if="collapsed">
        <img src="assets/svg/unfold.svg" class="min-w-[36px]" alt="" />
      </div>
      <div v-else>
        <img src="assets/svg/collapse.svg" class="min-w-[36px]" alt="" />
      </div>
    </button>
    <nav>
      <ul class="flex flex-col gap-10">
        <li v-for="item in navItems">
          <a :href="item.link">
            <div
              :class="{ 'bg-blue-50 font-normal': $route.path == item.link }"
              class="flex gap-4 px-4 py-2 hover:bg-blue-50 active:bg-blue-50 rounded-lg"
            >
              <img :src="item.icon" class="min-w-[28px]" alt="#" />
              <div
                class="whitespace-nowrap text-xl"
                :class="{ hidden: collapsed }"
              >
                {{ item.name }}
              </div>
            </div>
          </a>
        </li>
      </ul>
    </nav>
  </div>
</template>
