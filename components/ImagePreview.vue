<template>
  <div class="max-w-sm rounded shadow-lg m-10 items-center">
    <img class="object-fill" :src="require('@/assets/' + image + '')" />
    <div class="bg-green-100 px-6 py-4">
      <div class="text-xl mb-2 flex justify-center">
        <nuxt-link :to="route">{{ route.toUpperCase() }}</nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    image: {
      type: String,
      default: '',
    },
    route: {
      type: String,
      default: '/',
    },
  },
}
</script>
<style>
</style>