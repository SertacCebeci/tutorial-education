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
          question: 'What is the power unit of the cell?',
          options: ['Locoplast', 'Mithocondria'],
        },
        {
          question: 'When was the covid pandemic?',
          options: ['2010', '2019'],
        },
        {
          question: 'What do you need to survive?',
          options: ['Cola', 'Water'],
        },
      ],
      answers: [1, 1, 1],
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