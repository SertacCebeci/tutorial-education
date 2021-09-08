<template >
  <div>
    <h1 class="text-4xl bold m-5 font-serif text-green-700 pl-5">
      Free Education Program
    </h1>
    <h2 class="text-opacity-35 text-l pl-10">
      Please select the topic you wanna practise first:
    </h2>
    <br />
    <ul class="list-disc space-y-8 pl-10 text-red-800">
      <li><nuxt-link to="/history">History</nuxt-link></li>
      <li><nuxt-link to="/biology">Biology</nuxt-link></li>
      <li><nuxt-link to="/english">English</nuxt-link></li>
    </ul>
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
      title: 'Welcome to Free Education',
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
