<template>
  <div>
    <div v-if="product" class="pt-24 container mx-auto max-w-6xl flex flex-col space-y-8 py-5">
      <div class="flex justify-between w-full space-x-8">
        <img
          :src="`https://github.com/harblaith7/Nuxt-Crash-Course/blob/main/Client/assets/images/${product.image}?raw=true`"
          alt=""
          class="w-3/5 h-96"
        />
        <div class="border bg-gray-200 p-8 w-2/5 space-y-4">
          <h1 class="text-4xl font-bold">{{ product.title }}</h1>
          <p class="text-xl">{{ product.snippet }}</p>
          <RentModal :itemId="product.id"/>
          <!-- <RentModal :product="product" /> -->
        </div>
      </div>
      <div class="space-y-4">
        <div class="space-y-2">
          <h6 class="font-bold text-xl">Super Effective</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
        <div class="space-y-2">
          <h6 class="font-bold text-xl">Clean & Tidy</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
        <div class="space-y-2">
          <h6 class="font-bold text-xl">Cancel Anytime</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
        <div class="space-y-2">
          <h6 class="font-bold text-xl">Satisfaction Guaranteed</h6>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Asperiores,
            dolorem.
          </p>
        </div>
      </div>
      <div class="border-y py-8">
        <p>
          {{ product.description }}
        </p>
      </div>
      <Reviews />
    </div>
    <div v-else class="">
      <PageNotFound />
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    product() {
      return this.$store.getters.getProductById(this.$route.params.id);
    },
  },
};
</script>