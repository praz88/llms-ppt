<template>
    <div class="h-full w-full p-6 flex flex-col">
      <h2 class="text-2xl font-bold text-gray-200 mb-4">LLM Performance Comparison</h2>
      
      <div class="flex gap-4 mb-6 flex-wrap">
        <div class="space-y-2">
          <label class="text-gray-300 text-sm block">Metric</label>
          <select 
            v-model="selectedMetric"
            class="bg-gray-800 text-gray-200 rounded px-3 py-1 border border-gray-700"
          >
            <option v-for="[key, label] in Object.entries(metrics)" :key="key" :value="key">
              {{ label }}
            </option>
          </select>
        </div>
  
        <div class="space-y-2">
          <label class="text-gray-300 text-sm block">Model Type</label>
          <select 
            v-model="selectedType"
            class="bg-gray-800 text-gray-200 rounded px-3 py-1 border border-gray-700"
          >
            <option value="all">All Models</option>
            <option value="Open Source">Open Source</option>
            <option value="Closed Source">Closed Source</option>
          </select>
        </div>
  
        <div class="space-y-2">
          <label class="text-gray-300 text-sm block">Parameter Size</label>
          <select 
            v-model="parameterFilter"
            class="bg-gray-800 text-gray-200 rounded px-3 py-1 border border-gray-700"
          >
            <option v-for="[key, label] in Object.entries(parameterRanges)" :key="key" :value="key">
              {{ label }}
            </option>
          </select>
        </div>
  
        <div class="space-y-2">
          <label class="text-gray-300 text-sm block">Show Top</label>
          <select 
            v-model="showCount"
            class="bg-gray-800 text-gray-200 rounded px-3 py-1 border border-gray-700"
          >
            <option :value="5">Top 5</option>
            <option :value="10">Top 10</option>
            <option :value="20">Top 20</option>
          </select>
        </div>
      </div>
  
      <div class="flex-1 min-h-0 overflow-y-auto custom-scrollbar">
        <div v-for="model in filteredData" :key="model.gemini" 
             class="mb-2 bg-gray-800/50 p-3 rounded flex items-center gap-4">
          <div class="w-24 text-gray-300 font-medium">
            {{ model.gemini.split('-')[0] }}
          </div>
          <div class="flex-1 relative h-6 bg-gray-700/50 rounded">
            <div class="absolute top-0 left-0 h-full rounded"
                 :style="{
                   width: `${model[selectedMetric]}%`,
                   backgroundColor: model['Open Source'] === 'Yes' ? '#60A5FA' : '#8B5CF6'
                 }"
            ></div>
            <div class="absolute right-2 top-1/2 -translate-y-1/2 text-sm text-gray-300">
              {{ model[selectedMetric].toFixed(1) }}
            </div>
          </div>
          <div class="w-20 text-xs text-gray-400">
            {{ model.Parameters }}
          </div>
        </div>
      </div>

    </div>
  </template>
  
  <script setup>
  import { ref, computed } from 'vue'
  import llmsData from './llms.json'
  
  const selectedMetric = ref('Global Average')
  const selectedType = ref('all')
  const showCount = ref(10)
  const parameterFilter = ref('all')
  
  const metrics = {
    'Global Average': 'Global Score',
    'Reasoning Average': 'Reasoning',
    'Mathematics Average': 'Mathematics',
    'Data Analysis Average': 'Data Analysis',
    'Language Average': 'Language',
    'IF Average': 'Instruction Following'
  }
  
  const parameterRanges = {
    'all': 'All Sizes',
    'small': '< 10B',
    'medium': '10B - 100B',
    'large': '> 100B',
    'undisclosed': 'Not Disclosed'
  }
  
  const getParameterRange = (params) => {
    if (params === "Not Disclosed") return 'undisclosed'
    const size = parseInt(params)
    if (isNaN(size)) return 'undisclosed'
    if (size < 10) return 'small'
    if (size <= 100) return 'medium'
    return 'large'
  }
  
  const filteredData = computed(() => {
    return llmsData
      .filter(model => {
        if (selectedType.value !== 'all') {
          if (selectedType.value === 'Open Source' && model['Open Source'] !== 'Yes') return false
          if (selectedType.value === 'Closed Source' && model['Open Source'] !== 'No') return false
        }
        if (parameterFilter.value !== 'all') {
          return getParameterRange(model['Parameters']) === parameterFilter.value
        }
        return true
      })
      .sort((a, b) => b[selectedMetric.value] - a[selectedMetric.value])
      .slice(0, showCount.value)
  })
  </script>
  
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