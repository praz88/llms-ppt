<template>
  <div class="relative h-screen w-full overflow-hidden bg-[#0A1120] flex flex-col">
    <!-- Background stays same -->
    <div class="absolute inset-0 opacity-20">
      <div class="absolute inset-0 bg-gradient-to-br from-blue-500/10 via-purple-500/10 to-transparent">
        <div class="h-full w-full bg-[url('/grid.svg')] bg-center"></div>
      </div>
    </div>

    <!-- Particles stay same -->
    <div class="absolute inset-0">
      <div class="absolute h-2 w-2 bg-blue-400 rounded-full animate-float" style="top: 20%; left: 30%"></div>
      <div class="absolute h-2 w-2 bg-purple-400 rounded-full animate-float" style="top: 60%; left: 70%"></div>
      <div class="absolute h-2 w-2 bg-cyan-400 rounded-full animate-float" style="top: 80%; left: 40%"></div>
    </div>

    <!-- Content with reduced sizes -->
    <div class="relative z-10 flex-1 flex flex-col min-h-0">
      <div class="flex-1 flex items-center justify-center p-4">
        <div class="text-center">
          <h1 class="title-text text-4xl font-black tracking-tight bg-gradient-to-r from-blue-400 via-purple-400 to-cyan-400 text-transparent bg-clip-text mb-3">
            The AI Revolution
          </h1>
          
          <h2 class="title-text text-2xl font-bold text-gray-200 mb-3">
            Open Source vs Big Tech
          </h2>
          
          <p class="title-text text-sm text-gray-400 max-w-xl mx-auto">
            The defining technological battle of our generation
          </p>
        </div>
      </div>

      <!-- Footer with reduced padding -->
      <div class="p-4 flex justify-between text-gray-400 text-sm">
        <div>
          <div class="font-medium">Tech Talk November 2024</div>
          <div class="opacity-75">Bengaluru</div>
        </div>
        <div class="text-right">
          <div class="font-medium">Praz</div>
          <div class="opacity-75">Cofounder - Uprio</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
@keyframes float {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-20px); }
}

.animate-float {
  animation: float 6s ease-in-out infinite;
}
</style>