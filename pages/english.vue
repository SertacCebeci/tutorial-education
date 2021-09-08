<template>
  <div class="flex justify-center item-center">
    <div>
      <Question
        :question="cards[current].question"
        :options="cards[current].options"
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
      d: false,
      cards: [
        {
          question: 'Which one is grammatically correct?',
          options: [
            'Anyone can be the a hero',
            'They is staying on the ground.',
          ],
        },
        {
          question: '... are you doing?',
          options: ['How', 'Kind'],
        },
        {
          question: 'Who is a famous author?',
          options: ['John Doe', 'Dan Brown'],
        },
      ],
      answers: [1, 1, 0],
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
    done() {
      d = true
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