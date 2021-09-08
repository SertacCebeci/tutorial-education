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
          question: 'Who is the current USA president?',
          options: ['John Doe', 'Joe Biden'],
        },
        {
          question: 'When was the covid pandemic?',
          options: ['2010', '2019'],
        },
        {
          question: 'Who is the current France president?',
          options: ['John Doe', 'Macron'],
        },
      ],
      answers: ['Joe', '2019', 'Macron'],
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