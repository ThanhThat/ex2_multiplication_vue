<template>
  <div class="container">
    <div class="row mt-4">
      <div class="col col-12 col-md-6 offset-md-3">
        <form @submit.prevent="submitForm">
          <div class="score text-info h3">Score: {{ score }}</div>
          <div class="mb-3">
            <label for="answer" class="form-label h2 text-primary"
              >What is <span class="text-danger">{{ num1 }}</span> multiply by
              <span class="text-danger">{{ num2 }}</span
              >?</label
            >
            <input
              type="number"
              v-model="answer"
              id="answer"
              class="form-control"
              placeholder="Enter your answer"
              required
            />
          </div>
          <button class="btn btn-primary" type="submit">Submit</button>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      score: 0,
      num1: Math.round(Math.random() * 10),
      num2: Math.round(Math.random() * 10),
      answer: ''
    }
  },
  methods: {
    submitForm() {
      if (this.answer !== this.num1 * this.num2) {
        this.score--
      } else {
        this.score++
      }

      this.num1 = Math.round(Math.random() * 10)
      this.num2 = Math.round(Math.random() * 10)
      this.answer = ''
    }
  }
}
</script>

<style lang="scss" scoped></style>
