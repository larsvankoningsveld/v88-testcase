<template>
  <div class="h-screen grid grid-cols-[fit-content()_1fr] grid-rows-[fit-content()_1fr] ">
    <div class="bg-red-100 row-span-2">
      <Sidenav />
    </div>
    <div class="bg-blue-100">
      <Topbar />
    </div>
    <div class="bg-[#F2F7FA] px-28 py-22">
      <slot />
    </div>
    <div class="bg-grey-900 col-span-2 min-h-80 flex justify-center items-center">
      <h2 class="text-3xl text-white">
        Footer
      </h2>
    </div>
  </div>
</template>
