<script setup>
import { mockProjects } from '~/assets/data/ownProjects';

</script>
<template>
  <div>
    <div class="flex justify-between">
      <h1 class="text-4xl">Eigen projecten</h1>
      <button class="rounded-3xl px-4 py-2 bg-blue-900 text-white">
        + Nieuw project maken
      </button>
    </div>
    <div v-for="project in mockProjects">
      <OwnProject :project="project" />
    </div>
  </div>
</template>
