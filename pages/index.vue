<template >
  <div
    class="h-screen bg-gradient-to-r from-purple-200 via-blue-100 to-pink-350"
  >
    <h1 class="text-4xl bold m-5 font-serif text-green-700 pl-5">
      Free Education Program
    </h1>
    <h2 class="text-opacity-35 text-l pl-10">
      <br />
      Please select the topic you wanna practise first:
    </h2>
    <div class="flex flex-row items-center justify-center">
      <ImagePreview :image="elements[0].image" :route="elements[0].route" />
      <ImagePreview :image="elements[1].image" :route="elements[1].route" />
      <ImagePreview :image="elements[2].image" :route="elements[2].route" />
    </div>
  </div>
</template>

<script>
import AppHeader from '../components/AppHeader.vue'
import ImagePreview from '../components/ImagePreview.vue'
export default {
  components: {
    AppHeader,
    ImagePreview,
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
  data() {
    return {
      elements: [
        {
          image: 'History.png',
          route: 'history',
        },
        {
          image: 'biology.png',
          route: 'biology',
        },
        {
          image: 'eng.jpeg',
          route: 'english',
        },
      ],
    }
  },
}
</script>


 
