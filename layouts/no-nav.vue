<template>
  <div>
    <div class="pt-8 container mx-auto max-w-6xl flex flex-col space-y-8">
      <div>
        <NuxtLink
          class="px-4 inline py-2 text-sm font-medium leading-5 shadow text-white transition-colors duration-150 border border-transparent rounded-lg focus:outline-none focus:shadow-outline-blue bg-blue-600 active:bg-blue-600 hover:bg-blue-700"
          to="/"
          >Go Back</NuxtLink
        >
      </div>
    </div>
    <Nuxt />
  </div>
</template>
