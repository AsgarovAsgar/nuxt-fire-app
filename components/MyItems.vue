<template>
  <div class="flex justify-between space-x-4 w-full">
    <div class="w-1/4">
        <img class="h-full w-full object-cover rounded-md" :src="`https://github.com/harblaith7/Nuxt-Crash-Course/blob/main/Client/assets/images/${rent.image}?raw=true`" :alt="rent.title">
    </div>
    <div class="space-y-2 w-3/4">
        <h2 class="text-xl font-bold">{{ rent.title }}</h2>
        <p>{{ rent.description }}</p>
    </div>
  </div>
</template>

<script>
export default {
    props:['rent']

}
</script>

<style>

</style>