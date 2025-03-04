<script setup>
import { ref } from "vue";
import { mockProjects } from "~/assets/data/ownProjects";
import plus from "assets/svg/plus.svg";
import {
  systemList,
  sectorList,
  urgencyList,
  statusList,
} from "assets/data/filterLists";

const systems = ref(systemList);
const sectors = ref(sectorList);
const urgencies = ref(urgencyList);
const statuses = ref(statusList);
</script>

<template>
  <div>
    <div class="flex justify-between mb-16">
      <h1 class="text-5xl font-medium">Eigen projecten</h1>
      <a href="#" class="btn-primary items-center flex gap-4">
        <img class="w-[16px]" :src="plus" alt="+" />
        <span class="text-lg font-light"> Nieuw project maken </span>
      </a>
    </div>
    <div class="flex gap-4 mb-8">
      <Filter id="filter-1" label="Systeem" v-model="systems" />
      <Filter id="filter-2" label="Sector" v-model="sectors" />
      <Filter id="filter-3" label="Urgentie" v-model="urgencies" />
      <Filter id="filter-4" label="Status" v-model="statuses" />
    </div>
    <div class="grid grid-cols-2 gap-4">
      <div v-for="project in mockProjects">
        <OwnProject :project="project" />
      </div>
    </div>
  </div>
</template>
