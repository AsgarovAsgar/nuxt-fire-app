<template>
    <div class="flex flex-col space-y-2">
        <h2 class="text-4xl font-bold">{{ cardInfo.title }}</h2>
        <p class="text-2xl text-gray-700">{{ cardInfo.snippet }}</p>
        <div class="grid grid-cols-3 gap-4">
            <LargeCard v-for="card in cardInfo.cards" :key="card.id" :card="card" />
        </div>
    </div>
</template>

<script>
export default {
    props: ['cardInfo']
}
</script>

