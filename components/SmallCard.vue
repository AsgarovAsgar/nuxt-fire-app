<template>
<div>
    <NuxtLink :to="`/products/${card.id}`" class="flex flex-col">
        <img class="rounded-md h-48 w-full object-cover" :src="`https://github.com/harblaith7/Nuxt-Crash-Course/blob/main/Client/assets/images/${card.image}?raw=true`" :alt="card.title">
    </NuxtLink>
    </div>
</template>

<script>
export default {
    props:['card']
}
</script>