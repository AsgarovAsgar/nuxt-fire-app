<template>
<div>
  <div class="pt-24 container mx-auto max-w-6xl flex flex-col space-y-8">
    <LargeCardDisplay v-for="(largeCard, index) in largeCardSections.slice(0,1)" :key="index+'a'" :cardInfo="largeCard" />
    <SmallCardDisplay v-for="smallCard in smallCardSections" :key="smallCard.id" :cardInfo="smallCard" />
  </div>
</div>

</template>

<script>
import { largeCardSections, smallCardSections } from '@/assets/data.js'

export default {
    data() {
        return {
            largeCardSections,
            smallCardSections
        }
    }
}
</script>

<style>

</style>