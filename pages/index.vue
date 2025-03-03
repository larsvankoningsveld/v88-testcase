<script setup>
import { mockProjects } from "~/assets/data/ownProjects";
import plus from "assets/svg/plus.svg";

const systemList = [
  {
    label: "Systeem 1",
    checked: false,
  },
  {
    label: "Systeem 2",
    checked: false,
  },
  {
    label: "Systeem 3",
    checked: false,
  },
  {
    label: "Systeem 4",
    checked: false,
  },
  {
    label: "Systeem 5",
    checked: false,
  },
];

const sectorList = [
  {
    label: "Informatietechnologie (IT)",
    checked: false,
  },
  {
    label: "Financiële sector",
    checked: false,
  },
  {
    label: "Gezondheidszorg",
    checked: false,
  },
  {
    label: "Onderwijs",
    checked: false,
  },
  {
    label: "Overheid",
    checked: false,
  },
  {
    label: "Telecommunicatie",
    checked: false,
  },
  {
    label: "Detailhandel en E-commerce",
    checked: false,
  },
  {
    label: "Productie en Logistiek",
    checked: false,
  },
  {
    label: "Entertainment en Media",
    checked: false,
  },
];

const urgencyList = [
  {
    label: "Beetje urgent",
    checked: false,
  },
  {
    label: "Standaard urgent",
    checked: false,
  },
  {
    label: "Fucking urgent",
    checked: false,
  },
];

const statusList = [
  {
    label: "Open",
    checked: false,
  },
  {
    label: "In behandeling",
    checked: false,
  },
  {
    label: "Gesloten",
    checked: false,
  },
];
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
      <Filter id="filter-1" label="Systeem" :list="systemList" />
      <Filter id="filter-2" label="Sector" :list="sectorList" />
      <Filter id="filter-3" label="Urgentie" :list="urgencyList" />
      <Filter id="filter-4" label="Status" :list="statusList" />
    </div>
    <div class="grid grid-cols-2 gap-4">
      <div v-for="project in mockProjects">
        <OwnProject :project="project" />
      </div>
    </div>
  </div>
</template>
