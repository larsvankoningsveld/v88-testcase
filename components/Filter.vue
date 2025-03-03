<script setup>
const props = defineProps(["id", "label", "list"]);
import chevron from "assets/svg/chevron.svg";
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
    <div
      :id="id"
      class="inset-[unset] bg-white p-8 shadow rounded-xl relative mt-2"
      popover="auto"
    >
      <div v-for="item in list">
        <ul>
          <li class="flex gap-2 items-center">
            <input type="checkbox" :checked="item.checked" />
            <span>
              {{ item.label }}
            </span>
          </li>
        </ul>
      </div>
      <div class="flex gap-2">
        <button class="btn-secondary">Annuleer</button>
        <button class="btn-primary">Bevestigen</button>
      </div>
    </div>
  </div>
</template>
