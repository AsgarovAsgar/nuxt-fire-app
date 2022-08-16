<template>
  <div>
    <div class="pt-24 container mx-auto max-w-6xl flex flex-col space-y-8">
      <Hero />
      <LargeCardDisplay v-for="cardInfo in largeCardInfo" :key="cardInfo.id+ 'a'" :cardInfo="cardInfo" />
      <SmallCardDisplay v-for="cardInfo in smallCardInfo" :key="cardInfo.id" :cardInfo="cardInfo" />
    </div>
  </div>
</template>

<script>
import { largeCardSections, smallCardSections } from '@/assets/data.js'
export default {
  name: 'IndexPage',
    data() {
        return {
            largeCardInfo: largeCardSections,
            smallCardInfo: smallCardSections,
        }
    }
}
</script>