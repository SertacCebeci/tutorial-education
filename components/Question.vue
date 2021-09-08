<template>
  <div>
    <div class="flex justify-center p-10">
      <div>
        <div class="px-20 py-12 space-y-4 bg-gray-100 shadow-xl">
          <div>
            {{ question }}
            <div v-for="(option, index) in options" :key="index" class="mt-2">
              <input
                :id="'radio-' + index"
                type="radio"
                class="form-radio"
                name="accountType"
                @change="handleSelect(index)"
                :checked="selected === index"
              />
              <label :for="'radio-' + index" class="inline-flex items-center">
                <span class="ml-2">{{ option }}</span>
              </label>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="justify-center flex items-center">
      <button
        class="
          bg-blue-500
          hover:bg-blue-700
          text-white
          font-bold
          py-2
          px-4
          rounded
          flex
          justify-center
          items-center
          m-10
        "
        @click="handleBeforeButton"
      >
        Before
      </button>
      <button
        class="
          bg-blue-500
          hover:bg-blue-700
          text-white
          font-bold
          py-2
          px-4
          rounded
          flex
          justify-center
          items-center
        "
        @click="handleNextButton"
      >
        Next
      </button>
    </div>
    <div v-if="selected < 0" class="flex justify-center text-red-600 italic">
      ***You should select an option***
    </div>
    <div v-if="selected >= 0">Result: {{ this.scorePercent }}%</div>
  </div>
</template>

<script>
export default {
  name: 'Question',
  data() {
    return {
      selected: -1,
      scoreCount: 0,
      scorePercent: 100,
    }
  },
  props: {
    question: {
      type: String,
      default: '?',
    },
    options: {
      type: Array,
      default: [],
    },
    answers: {
      type: Number,
      default: 0,
    },
  },
  methods: {
    handleNextButton() {
      if (this.selected >= 0) {
        this.$emit('nextClicked')
        if (this.selected == this.answers) {
          this.scoreCount = this.scoreCount + 1
          this.scorePercent = (this.scorePercent * this.scoreCount) / 3
        }
        this.selected = -1
      }
    },
    handleBeforeButton() {
      this.$emit('beforeClicked')
    },
    handleSelect(index) {
      this.selected = index
      console.log(this.selected)
    },
    checkAnswers() {},
  },
}
</script>

<style>
</style>