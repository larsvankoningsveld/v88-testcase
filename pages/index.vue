<script setup>
import { mockProjects } from '~/assets/data/ownProjects';
import plus from "assets/svg/plus.svg"
</script>

<template>
  <div>
    <div class="flex justify-between mb-16">
      <h1 class="text-5xl font-medium">Eigen projecten</h1>
      <a href="#" class="hover:cursor-pointer rounded-3xl items-center flex gap-4 px-8 py-2 bg-blue-900 text-white">
        <img class="w-[16px]" :src="plus" alt="+">
        <span class="text-lg font-light">
          Nieuw project maken
        </span>
      </a>
    </div>
    <div class="grid grid-cols-2 gap-4">
      <div v-for="project in mockProjects">
        <OwnProject :project="project" />
      </div>
    </div>
  </div>
</template>
