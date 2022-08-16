<template>
  <div class="flex space-x-4">
    <div>
        <img class="h-14 w-14 rounded-full flex-shrink-0" :src="reviewer.picture.medium" alt="">
    </div>
    <div>
        <h4 class="text-md font-bold">{{ reviewer.login.username }}</h4>
        <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. Velit beatae omnis repudiandae eos?</p>
    </div>
  </div>
</template>

<script>
export default {
    props:['reviewer']

}
</script>

<style>

</style>