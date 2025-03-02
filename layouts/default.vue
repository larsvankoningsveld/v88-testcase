<template>
  <main class="h-screen grid grid-cols-[13rem_1fr] grid-rows-[4.5rem_1fr] grid-">
    <div class="bg-red-100 row-span-2">
      <Sidenav />
    </div>
    <div class="bg-blue-100">
      <Topbar />
    </div>
    <div class="bg-green-100 p-16">
      <slot />
    </div>
  </main>
  <div class="bg-grey-900 col-span-2 min-h-80 flex justify-center items-center">
    <h2 class="text-3xl text-white">
      Footer
    </h2>
  </div>
</template>
