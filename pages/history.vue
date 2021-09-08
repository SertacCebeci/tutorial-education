<template>
  <div class="flex justify-center item-center">
    <div>
      <Question
        :question="cards[current].question"
        :options="cards[current].options"
        @nextClicked="changeCard"
        @beforeClicked="previousQuestion"
      />
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
      >
        See result
      </button>
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
          question: 'Who is the current president?',
          options: ['John Doe', 'Joe'],
        },
        {
          question: 'Fark eder mi?',
          options: ['Evet', 'Hayır'],
        },
        {
          question: 'Who is the current president?',
          options: ['John Doe', 'Joe'],
        },
      ],
      answers: ['Joe', 'Hayır', 'Joe'],
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