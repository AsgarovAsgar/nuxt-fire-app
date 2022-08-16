<template>
    <div class="flex flex-col space-y-4">
        <h2 class="text-4xl font-bold">{{ cardInfo.title }}</h2>
        <div class="grid grid-cols-4 gap-4">
            <SmallCard v-for="card in cardInfo.cards" :key="card.id" :card="card" />
        </div>
    </div>
</template>

<script>
export default {
    props: ['cardInfo']
}
</script>

