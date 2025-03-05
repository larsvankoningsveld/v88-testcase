<script setup>
import { ref, computed } from "vue";
import { mockProjects } from "~/assets/data/ownProjects";
import plus from "assets/svg/plus.svg";
import {
  systemList,
  sectorList,
  urgencyList,
  statusList,
} from "assets/data/filterLists";

const systems = ref(JSON.parse(JSON.stringify(systemList)));
const sectors = ref(JSON.parse(JSON.stringify(sectorList)));
const urgencies = ref(JSON.parse(JSON.stringify(urgencyList)));
const statuses = ref(JSON.parse(JSON.stringify(statusList)));

const allProjects = ref(JSON.parse(JSON.stringify(mockProjects)));

const filteredProjects = computed(() => filterSystems(allProjects.value));

function filterSystems(projects) {
  // If is at least one filter checked
  if (systems.value.some((filter) => filter.checked === true)) {
    // Capture those filters in an array
    const filters = JSON.parse(
      JSON.stringify(systems.value.filter((filter) => filter.checked === true)),
    );
    // Filter projects such that...
    const result = projects.filter((project) =>
      // ...it only returns projects with a checked filter
      filters.forEach((filter) =>
        filter.label === project.system ? true : false,
      ),
    );
    console.log(result);
    return result;
    // If no filters are checked return all projects
  } else return projects;
}

function updateSystems(event) {
  console.log(JSON.parse(JSON.stringify(event.value)));
  systems.value = JSON.parse(JSON.stringify(event.value));
}
function updateSectors(event) {
  sectors.value = JSON.parse(JSON.stringify(event.value));
}
function updateUrgencies(event) {
  urgencies.value = JSON.parse(JSON.stringify(event.value));
}
function updateStatuses(event) {
  statuses.value = JSON.parse(JSON.stringify(event.value));
}
</script>

<template>
  <div>
    <div class="flex justify-between mb-16">
      <h1 class="text-5xl font-medium">Eigen projecten</h1>
      <a href="#" class="btn-primary items-center flex gap-4">
        <img class="w-[16px]" :src="plus" alt="+" />
        <span class="text-lg font-light">Nieuw project maken</span>
      </a>
    </div>
    {{ systems }}
    <div class="flex gap-4 mb-8">
      <Filter
        id="systems"
        label="Systeem"
        @update="updateSystems"
        :list="systems"
      />
      <Filter
        id="sectors"
        label="Sector"
        @update="updateSectors"
        :list="sectors"
      />
      <Filter
        id="urgencies"
        label="Urgentie"
        @update="updateUrgencies"
        :list="urgencies"
      />
      <Filter
        id="statuses"
        label="Status"
        @update="updateStatuses"
        :list="statuses"
      />
    </div>
    <div class="grid grid-cols-2 gap-4">
      <div v-for="project in allProjects">
        <OwnProject :project="project" />
      </div>
    </div>
  </div>
</template>
