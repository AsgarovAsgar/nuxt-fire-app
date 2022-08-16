<template>
  <div class="pt-4 container mx-auto max-w-6xl flex flex-col space-y-8">
    <MyItems v-for="rent in customerRentals" :key="rent.id" :rent="rent" />
  </div>
</template>

<script>

export default {
  layout: 'no-nav',
  computed: {
    customerRentals () {
      return this.$store.state.customerRentals
    }
  }

}
</script>

<style>

</style>