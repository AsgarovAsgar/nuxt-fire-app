<template>
  <div>
    <div class="flex space-x-8 items-center">
      <h3 class="text-xl font-bold">Customer Reviews</h3>

      <button
        @click="$fetch"
        class="p-1 hover:bg-gray-100 rounded-full duration-300 transition text-blue-500"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-6 w-6"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15"
          />
        </svg>
      </button>
    </div>
    <div class="pt-4">
      <p v-if="$fetchState.pending">Fetching customer reviews...</p>
      <p v-else-if="$fetchState.error">An error occurred :(</p>
      <div v-else>
        <ul class="space-y-4">
          <ReviewCard
            v-for="reviewer of reviewers"
            :key="reviewer.login.uuid"
            :reviewer="reviewer"
          >
            {{ reviewer.gender }}
          </ReviewCard>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      reviewers: [],
    };
  },
  //  async fetch() {
  //       this.reviewers = await fetch(
  //         'https://randomuser.me/api/?results=5'
  //       ).then(res => res.json())
  //     },
  async fetch() {
    await this.getReviewers();
  },
  methods: {
    async getReviewers() {
      const data = axios.get("https://randomuser.me/api/?results=5");
      const result = await data;
      this.reviewers = result.data.results;
    },
  },
};
</script>

<style></style>
