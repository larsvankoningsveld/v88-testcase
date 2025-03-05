<script setup>
import { ref } from "vue";
import chevron from "assets/svg/chevron.svg";
const emit = defineEmits("update");

const props = defineProps(["id", "label", "list"]);
let temp = JSON.parse(JSON.stringify(props.list));
const newList = ref(JSON.parse(JSON.stringify(props.list)));

function undo() {
  newList.value = JSON.parse(JSON.stringify(temp));
}

function update() {
  temp = JSON.parse(JSON.stringify(newList.value));
  emit("update", { value: newList });
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
    {{ newList }}
    <div
      :id="id"
      class="inset-[unset] bg-white p-6 shadow rounded-xl relative mt-2"
      popover="auto"
    >
      <ul class="mb-6">
        <li
          v-for="(filter, index) in newList"
          class="flex gap-4 text-lg py-2 items-center border-grey-100 not-last:border-b"
        >
          <input
            :name="filter.label"
            type="checkbox"
            role="checkbox"
            v-model="newList[index].checked"
          />
          <label :for="filter.label">
            {{ filter.label }}
          </label>
        </li>
      </ul>
      <div class="flex gap-2">
        <button @click="undo" :popovertarget="id" class="btn-secondary">
          Annuleer
        </button>
        <button @click="update" class="btn-primary" :popovertarget="id">
          Bevestigen
        </button>
      </div>
    </div>
  </div>
</template>
