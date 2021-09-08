<template>
  <div class="p-1 border-4 border-light-blue-500 border-opacity-25 m-3">
    <p class="text-blue-700 text-base">{{ joke }}</p>
  </div>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke, id'],
}
</script>

<style>
</style>