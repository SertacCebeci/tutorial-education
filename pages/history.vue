<template>
  <div class="flex justify-center item-center">
    <div>
      <Question
        :question="cards[current].question"
        :options="cards[current].options"
        :answers="cards[current].answer"
        @nextClicked="changeCard"
        @beforeClicked="previousQuestion"
      />
      <nuxt-link to="/score">
        <button
          class="
            bg-yellow-300
            hover:opacity-70
            text-gray-500
            font-bold
            py-2
            px-4
            rounded
            mr-4
          "
          v-if="finished"
          @click="handleResults"
        >
          See result
        </button>
      </nuxt-link>
    </div>
  </div>
</template>

<script>
import Question from '@/components/Question'
export default {
  components: {
    Question,
  },
  data() {
    return {
      current: 0,
      cards: [
        {
          question: 'Who is the current USA president?',
          options: ['John Doe', 'Joe Biden'],
          answers: 0,
        },
        {
          question: 'When was the covid pandemic?',
          options: ['2010', '2019'],
          answers: 0,
        },
        {
          question: 'Who is the current France president?',
          options: ['John Doe', 'Macron'],
          answers: 0,
        },
      ],
    }
  },
  methods: {
    changeCard() {
      if (!this.finished) {
        this.current = this.current + 1
      }
    },
    previousQuestion() {
      if (this.current != 0) {
        this.current = this.current - 1
      }
    },
    handleResults() {
      this.$emit('finishedClicked')
      console.log('done clicked')
    },
  },
  computed: {
    finished() {
      return this.current === this.cards.length - 1
    },
  },
}
</script>

<style>
</style>