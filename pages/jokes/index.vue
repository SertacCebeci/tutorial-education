<template>
  <div class="text-xl text-red-600 italic m-10">
    Please select a lesson to see question list.
  </div>
</template>

<script>
import axios from 'axios'
import AppHeader from '../../components/AppHeader.vue'
import Joke from '../../components/Joke.vue'
export default {
  components: {
    Joke,
  },
  data() {
    return { jokes: [] }
  },
  async created() {
    const config = {
      headers: {
        Accept: 'application/json',
      },
    }
    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results
    } catch (e) {
      console.log(e)
    }
  },
  head() {
    return {
      title: 'Dad Jokes',
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