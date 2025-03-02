<script setup>
const props = defineProps(['project'])
</script>
<template>
  <div class="bg-white rounded-xl shadow p-8 flex flex-col gap-4">
    <div class="flex justify-between">
      <div id="title-section" class=" border-l-4 border-orange-300 px-2 grow flex flex-col gap-2">
        <div class="font-bold text-xl">
          {{ project.title }}
        </div>
        <div class="text-lg">
          {{ project.system }}
        </div>
        <div class="flex gap-24">
          <div class="flex flex-col">
            <div class="text-sm">
              {{ project.sector }}
            </div>
            <div class="font-bold">
              {{ project.sector }}
            </div>
          </div>
          <div class="flex flex-col">
            <div class="text-sm">
              {{ project.sector }}
            </div>
            <div class="font-bold">
              {{ project.sector }}
            </div>
          </div>
        </div>
      </div>
      <div id="status">
        {{ project.status }}
      </div>
    </div>
    <div id="desc">{{ project.desc }}</div>
    <div>
      <a href="#" class="rounded-3xl bg-green-500 px-6 py-2 text-white">
        Meer informatie
      </a>
    </div>
  </div>
</template>
