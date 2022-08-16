<template>
<div>
    <NuxtLink :to="`/products/${card.id}`" class="flex flex-col space-y-2">
        <img class="rounded-md h-48 w-full object-cover" :src="`https://github.com/harblaith7/Nuxt-Crash-Course/blob/main/Client/assets/images/${card.image}?raw=true`" :alt="card.title">
        <h3 class="text-xl font-bold">{{ card.title }}</h3>
        <p class="text-gray-500">{{ card.snippet }}</p>
        <!-- https://github.com/harblaith7/Nuxt-Crash-Course/blob/main/Client/assets/images/fe1.jpg?raw=true -->
    </NuxtLink>
</div>
</template>

<script>
export default {
    props:['card']
}
</script>