<script setup>
import { ref } from 'vue'

const currentQuestion = ref(0)
const showResults = ref(false)
const votes = ref({
  q1: { 'Open Source': 0, 'Closed Source': 0, 'Hybrid': 0 },
  q2: { 'Performance': 0, 'Cost': 0, 'Customization': 0, 'Security': 0 },
  q3: { 'Yes': 0, 'No': 0, 'Maybe': 0 }
})

const questions = [
  {
    text: "What type of LLM are you currently using?",
    options: ['Open Source', 'Closed Source', 'Hybrid'],
    id: 'q1'
  },
  {
    text: "What's your primary concern when choosing an LLM?",
    options: ['Performance', 'Cost', 'Customization', 'Security'],
    id: 'q2'
  }
]

const vote = (questionId, option) => {
  votes.value[questionId][option]++
  showResults.value = true
}

const nextQuestion = () => {
  if (currentQuestion.value < questions.length - 1) {
    currentQuestion.value++
    showResults.value = false
  }
}

const prevQuestion = () => {
  if (currentQuestion.value > 0) {
    currentQuestion.value--
    showResults.value = false
  }
}

const getPercentage = (questionId, option) => {
  const questionVotes = votes.value[questionId]
  const total = Object.values(questionVotes).reduce((a, b) => a + b, 0)
  return total === 0 ? 0 : Math.round((questionVotes[option] / total) * 100)
}

const getTotalVotes = (questionId) => {
  return Object.values(votes.value[questionId]).reduce((a, b) => a + b, 0)
}
</script>

<template>
  <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-8">
    <div class="flex-1 overflow-y-auto custom-scrollbar px-4 -mx-4">
      <div class="max-w-2xl mx-auto">
        <h3 class="text-xl text-gray-200 mb-6">{{ questions[currentQuestion].text }}</h3>

        <div class="space-y-4 mb-6">
          <div v-for="option in questions[currentQuestion].options" :key="option"
               @click="vote(questions[currentQuestion].id, option)"
               class="bg-gray-800/50 rounded-lg p-4 cursor-pointer hover:bg-gray-700/50 transition-colors">
            <div class="flex justify-between items-center">
              <span class="text-gray-200">{{ option }}</span>
              <span v-if="showResults" class="text-gray-400">
                {{ getPercentage(questions[currentQuestion].id, option) }}%
              </span>
            </div>
            <div v-if="showResults" class="mt-2 bg-gray-700/30 h-2 rounded-full overflow-hidden">
              <div class="h-full bg-blue-500 transition-all duration-1000"
                   :style="{ width: getPercentage(questions[currentQuestion].id, option) + '%' }">
              </div>
            </div>
          </div>
        </div>

        <div class="text-center text-gray-400 mb-8">
          <p v-if="showResults">
            Total votes: {{ getTotalVotes(questions[currentQuestion].id) }}
          </p>
        </div>
      </div>
    </div>

    <!-- Fixed Navigation Footer -->
    <div class="mt-6 pt-4 border-t border-gray-800 flex justify-between">
      <button @click="prevQuestion"
              :disabled="currentQuestion === 0"
              :class="{ 'opacity-50 cursor-not-allowed': currentQuestion === 0 }"
              class="px-4 py-2 bg-gray-800 rounded text-gray-200 hover:bg-gray-700">
        Previous
      </button>
      <div class="flex items-center space-x-2">
        <div v-for="(_, index) in questions" :key="index" 
             class="w-2 h-2 rounded-full"
             :class="currentQuestion === index ? 'bg-blue-500' : 'bg-gray-600'">
        </div>
      </div>
      <button @click="nextQuestion"
              :disabled="currentQuestion === questions.length - 1"
              :class="{ 'opacity-50 cursor-not-allowed': currentQuestion === questions.length - 1 }"
              class="px-4 py-2 bg-gray-800 rounded text-gray-200 hover:bg-gray-700">
        Next
      </button>
    </div>
  </div>
</template>

<style scoped>
.custom-scrollbar::-webkit-scrollbar {
  width: 8px;
}

.custom-scrollbar::-webkit-scrollbar-track {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
}

.custom-scrollbar::-webkit-scrollbar-thumb {
  background: rgba(255, 255, 255, 0.2);
  border-radius: 4px;
}

.custom-scrollbar::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 255, 255, 0.3);
}
</style>