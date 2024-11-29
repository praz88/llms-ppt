<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'

onMounted(() => {
  const timeline = gsap.timeline({ defaults: { duration: 0.7, ease: 'power2.out' }})
  
  timeline
    .from('h2', { y: -20, opacity: 0 })
    .from('.left-column > div', { 
      y: 20, 
      opacity: 0, 
      stagger: 0.2 
    }, '-=0.3')
    .from('.right-column > div', { 
      y: 20, 
      opacity: 0, 
      stagger: 0.2 
    }, '-=0.5')
})
</script>

<template>
  <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-8">
    <h2 class="text-2xl font-bold text-gray-200 mb-6">The LLM Landscape</h2>

    <div class="flex-1 overflow-y-auto custom-scrollbar grid grid-cols-2 gap-8">
      <!-- Left Column -->
      <div class="left-column space-y-6">
        <div class="bg-gray-900/50 rounded-lg p-6">
          <h3 class="text-xl text-blue-400 mb-4">What are LLMs?</h3>
          <div class="text-gray-300 space-y-3">
            <p>• AI models trained on massive text datasets</p>
            <p>• Can understand and generate human-like text</p>
            <p>• Power modern AI applications</p>
            <p>• Range from 1B to 1T+ parameters</p>
          </div>
        </div>

        <div class="bg-gray-900/50 rounded-lg p-6">
          <h3 class="text-xl text-blue-400 mb-4">The Ecosystem</h3>
          <div class="space-y-2">
            <div class="flex items-center gap-3">
              <div class="w-3 h-3 rounded-full bg-purple-500"></div>
              <span class="text-gray-300">Cloud APIs (OpenAI, Anthropic, Google)</span>
            </div>
            <div class="flex items-center gap-3">
              <div class="w-3 h-3 rounded-full bg-blue-500"></div>
              <span class="text-gray-300">Open Source (Llama, Mistral, Gemma)</span>
            </div>
            <div class="flex items-center gap-3">
              <div class="w-3 h-3 rounded-full bg-green-500"></div>
              <span class="text-gray-300">Fine-tuned Solutions</span>
            </div>
            <div class="flex items-center gap-3">
              <div class="w-3 h-3 rounded-full bg-yellow-500"></div>
              <span class="text-gray-300">Hybrid Approaches</span>
            </div>
          </div>
        </div>
      </div>

      <!-- Right Column -->
      <div class="right-column space-y-6">
        <div class="bg-gray-900/50 rounded-lg p-6">
          <h3 class="text-xl text-purple-400 mb-4">Key Considerations</h3>
          <div class="grid grid-cols-2 gap-4">
            <div class="space-y-2">
              <div class="text-gray-200 font-medium">Performance</div>
              <div class="text-gray-400 text-sm">Accuracy, speed, and quality of outputs</div>
            </div>
            <div class="space-y-2">
              <div class="text-gray-200 font-medium">Cost</div>
              <div class="text-gray-400 text-sm">Infrastructure, API calls, maintenance</div>
            </div>
            <div class="space-y-2">
              <div class="text-gray-200 font-medium">Control</div>
              <div class="text-gray-400 text-sm">Customization and data privacy</div>
            </div>
            <div class="space-y-2">
              <div class="text-gray-200 font-medium">Integration</div>
              <div class="text-gray-400 text-sm">Ease of deployment and scaling</div>
            </div>
          </div>
        </div>

        <div class="bg-gray-900/50 rounded-lg p-6">
          <h3 class="text-xl text-purple-400 mb-4">Current Trends</h3>
          <div class="text-gray-300 space-y-3">
            <p>• Smaller, more efficient models</p>
            <p>• Multi-modal capabilities</p>
            <p>• Specialized domain models</p>
            <p>• Focus on responsible AI</p>
          </div>
        </div>
      </div>
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