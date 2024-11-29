<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'

onMounted(() => {
  const timeline = gsap.timeline({ defaults: { duration: 0.7, ease: 'power2.out' }})
  
  timeline
    .to('.message-1', { opacity: 1, y: 0, duration: 0.7 })
    .to('.message-2', { opacity: 1, y: 0, duration: 0.7 }, '+=0.5')
    .to('.message-3', { opacity: 1, y: 0, duration: 0.7 }, '+=1')
    .to('.message-4', { opacity: 1, y: 0, duration: 0.7 }, '+=0.5')
    .to('.tagline', { opacity: 1, y: 0, duration: 0.7 }, '+=0.5')
})
</script>

<template>
  <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-8">
    <!-- Chat Interface -->
    <div class="flex-1 overflow-y-auto space-y-6 custom-scrollbar">
      <!-- Message 1 -->
      <div class="flex items-start space-x-4 opacity-0 message-1">
        <div class="w-10 h-10 rounded-full bg-blue-500 flex items-center justify-center text-white font-bold">
          H
        </div>
        <div class="flex-1">
          <div class="bg-gray-800 rounded-lg p-4 max-w-[80%]">
            <p class="text-gray-200">Hey AI, what's 2+2?</p>
          </div>
          <span class="text-gray-400 text-sm mt-1 block">Human, 2023</span>
        </div>
      </div>

      <!-- Message 2 -->
      <div class="flex items-start space-x-4 justify-end opacity-0 message-2">
        <div class="flex-1">
          <div class="bg-purple-900/50 rounded-lg p-4 max-w-[80%] ml-auto">
            <p class="text-gray-200">According to my advanced neural networks and sophisticated mathematical algorithms, after careful analysis and consideration of various numerical systems and mathematical frameworks, I can confidently state that the sum of the integers 2 and 2 equals 4.</p>
          </div>
          <span class="text-gray-400 text-sm mt-1 block text-right">AI Assistant, 2023</span>
        </div>
        <div class="w-10 h-10 rounded-full bg-purple-500 flex items-center justify-center text-white font-bold">
          AI
        </div>
      </div>

      <!-- Message 3 -->
      <div class="flex items-start space-x-4 opacity-0 message-3">
        <div class="w-10 h-10 rounded-full bg-blue-500 flex items-center justify-center text-white font-bold">
          H
        </div>
        <div class="flex-1">
          <div class="bg-gray-800 rounded-lg p-4 max-w-[80%]">
            <p class="text-gray-200">Hey AI, can you choose between these LLMs?</p>
          </div>
          <span class="text-gray-400 text-sm mt-1 block">Product Manager, 2024</span>
        </div>
      </div>

      <!-- Message 4 -->
      <div class="flex items-start space-x-4 justify-end opacity-0 message-4">
        <div class="flex-1">
          <div class="bg-purple-900/50 rounded-lg p-4 max-w-[80%] ml-auto">
            <p class="text-gray-200">*nervous AI noises* 😅</p>
          </div>
          <span class="text-gray-400 text-sm mt-1 block text-right">AI Assistant, 2024</span>
        </div>
        <div class="w-10 h-10 rounded-full bg-purple-500 flex items-center justify-center text-white font-bold">
          AI
        </div>
      </div>
    </div>

    <!-- Bottom Tag -->
    <div class="text-center mt-8 opacity-0 tagline">
      <p class="text-xl text-gray-200 font-medium">"Choosing an LLM shouldn't be harder than basic math."</p>
      <p class="text-gray-400 mt-2">Let's make it simple.</p>
    </div>
  </div>
</template>

<style scoped>
.message-1, .message-2, .message-3, .message-4, .tagline {
  transform: translateY(20px);
}

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