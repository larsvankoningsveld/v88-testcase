<script setup>
const props = defineProps(['project'])
</script>
<template>
  <div class="bg-white rounded-xl p-4 flex flex-col gap-4">
    <div class="flex justify-between">
      <div id="title-section" class="grow">
        <div class="font-bold text-xl">
          {{ project.title }}
        </div>
        <div class="text-lg">
          {{ project.system }}
        </div>
        <div class="flex justify-between">
          <div class="flex flex-col">
            <div class="font-bold">
              {{ project.sector }}
            </div>
            <div class="text-sm">
              {{ project.sector }}
            </div>
          </div>
          <div class="flex flex-col">
            <div class="font-bold">
              {{ project.sector }}
            </div>
            <div class="text-sm">
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
