<template >
  <div>
    <AppHeader />
    <nuxt />
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
      title: 'Free ED',
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