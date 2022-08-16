<template>
    <div class="text-blue-500 py-3 flex justify-between container mx-auto max-w-6xl">
        <NuxtLink id="v-step-0" to="/" class="text-2xl" href="">Fire Flies</NuxtLink>
        
        <div class="space-x-4">
            <NuxtLink class="v-step-1" to="/products">Products</NuxtLink>
            <NuxtLink data-v-step="2" to="/my-items">My items</NuxtLink>
        </div>
    <v-tour name="myTour" :steps="steps"></v-tour>

    </div>
</template>

<script>
export default {
    data() {
        return {
            steps: [
        {
          target: "#v-step-0", // We're using document.querySelector() under the hood
          header: {
            title: "Get Started",
          },
          content: `Discover <strong>Fire Flies</strong>!`,
        },
        {
          target: ".v-step-1",
          content: "Here you can see our products",
        },
        {
          target: '[data-v-step="2"]',
          content:
            "Your items will be saved here!<br>You can buy or rent them",
          params: {
            placement: "top", // Any valid Popper.js placement. See https://popper.js.org/popper-documentation.html#Popper.placements
          },
        },
      ],
        }
    },
    mounted: function () {
    this.$tours["myTour"].start();
  },
}
</script>

<style>
.v-step {
  border: 3px solid red;
}
.v-step__buttons {
  border: 3px solid red;

}
</style>
