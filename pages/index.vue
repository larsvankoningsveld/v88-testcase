<script setup>
import { ref } from 'vue'
const mockProjects = ref([
  {
    anonymous: true,
    title: 'Legacy title',
    desc: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
    links: [],
    files: [],
    system: 'Legacy system',
    urgency: 0,
    urgencyDesc: '',
    budget: 0,
    budgetKnown: true
  },
  {
    anonymous: true,
    title: 'Legacier title',
    desc: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
    links: [],
    files: [],
    system: 'Legacier system',
    urgency: 1,
    urgencyDesc: '',
    budget: 2,
    budgetKnown: true
  },
  {
    anonymous: true,
    title: 'Legaciest title',
    desc: 'Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry\'s standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book.It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.',
    links: [],
    files: [],
    system: 'Legaciest system',
    urgency: 2,
    urgencyDesc: '',
    budget: 3,
    budgetKnown: true
  }
])

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
      {{ project.title }}
    </div>
  </div>
</template>
