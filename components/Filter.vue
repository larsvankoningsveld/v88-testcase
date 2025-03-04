<script setup>
const props = defineProps(["id", "label"]);
const list = defineModel();

import chevron from "assets/svg/chevron.svg";
function update() {
  list.value[0].checked = !list.value[0].checked;
  console.log(list.value[0].target);
}
</script>

<template>
  <div class="relative">
    <button
      class="flex gap-4 hover:cursor-pointer items-center hover:shadow-lg active:shadow-md px-4 py-1 rounded-lg bg-white shadow text-grey-400"
      :popovertarget="id"
    >
      <div>
        {{ label }}
      </div>
      <img :src="chevron" alt="#" class="w-[24px]" />
    </button>
    <div>I am {{ list }}</div>
    <div
      :id="id"
      class="inset-[unset] bg-white p-6 shadow rounded-xl relative mt-2"
      popover="auto"
    >
      <ul class="mb-6">
        <li
          v-for="item in list.value"
          class="flex gap-4 text-lg py-2 items-center border-grey-100 not-last:border-b"
        >
          <input type="checkbox" role="checkbox" :checked="item.checked" />
          <span>
            {{ item.label }}
          </span>
        </li>
      </ul>
      <div class="flex gap-2">
        <button class="btn-secondary">Annuleer</button>
        <button @click="update" class="btn-primary">Bevestigen</button>
      </div>
    </div>
  </div>
</template>
