<template>
  <div>
    <h1 class="text-3xl bold m-5">About</h1>
    <p class="italic text-xl font-serif text-red-700 pl-5">
      This app helps you to prepare your lessons while taking a quiz.
    </p>
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'

export default {
  components: {
    AppHeader,
  },
  head() {
    return {
      title: 'About the App',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for dad jokes',
        },
      ],
    }
  },
}
</script>

<style>
</style>