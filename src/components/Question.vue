<script>
export default {
  props: {
    question: {
      type: String,
      required: true,
    },
    options: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      selectedOption: '',
    }
  },
  watch: {
    selectedOption(newValue) {
      // Emit event to parent component with the question and the selected option
      this.$emit('updateAnswer', { question: this.question, answer: newValue })
    },
  },
}
</script>

<template>
  <div class="question">
    <p>{{ question }}</p>
    <ul class="options-grid">
      <li v-for="(option, index) in options" :key="index">
        <label>
          <input
            v-model="selectedOption"
            type="radio"
            :name="question"
            :value="option"
          >
          {{ option }}
        </label>
      </li>
    </ul>
  </div>
</template>

<style>
.question {
  margin-bottom: 20px;
}
.question p {
  font-weight: bold;
}
.question ul {
  list-style-type: none;
  padding: 0;
}
.question li {
  margin: 5px 0;
}
.options-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2px;
  padding: 0;
  list-style: none;
}

.options-grid li {
  margin: 5px 0;
}
</style>
