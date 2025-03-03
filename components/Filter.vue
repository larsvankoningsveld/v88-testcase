<script setup>
const props = defineProps(['id'])

</script>

<template>
  <div class="relative">
    <button class="px-6 py-1 rounded bg-white shadow text-grey-500" :popovertarget="id">Greet me</button>
    <div :id="id" class="inset-[unset] bg-white p-16 shadow rounded-xl relative mt-2" popover="auto">Hi there!
    </div>
  </div>
</template>
