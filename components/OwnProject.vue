<script setup>
const props = defineProps(["project"]);
</script>
<template>
  <div class="bg-white rounded-xl shadow p-8 flex flex-col gap-6">
    <div class="flex justify-between">
      <div
        id="title-section"
        :class="project.status === 0 ? 'border-orange-300' : 'border-blue-200'"
        class="border-l-4 px-3 grow flex flex-col gap-2"
      >
        <div class="font-bold text-2xl">
          {{ project.title }}
        </div>
        <div class="text-xl">
          {{ project.system }}
        </div>
        <div class="flex gap-38">
          <div class="flex flex-col">
            <div class="text-sm text-grey-300">Sector</div>
            <div class="font-bold">
              {{ project.sector }}
            </div>
          </div>
          <div class="flex flex-col">
            <div class="text-sm text-grey-300">Sector</div>
            <div class="font-bold">
              {{ project.sector }}
            </div>
          </div>
        </div>
      </div>
      <div id="status">
        <div
          v-if="project.status === 0"
          class="text-sm bg-orange-300 text-orange-900 px-6 py-1 rounded-full"
        >
          Draft
        </div>
        <div
          v-else
          class="text-sm bg-blue-200 text-bue-800 px-6 py-1 rounded-full"
        >
          Open
        </div>
      </div>
    </div>
    <div id="desc">{{ project.desc }}</div>
    <div>
      <a
        href="#"
        class="rounded-3xl text-lg font-weight-extralight bg-green-500 px-6 py-2 text-white"
      >
        Meer informatie
      </a>
    </div>
  </div>
</template>
