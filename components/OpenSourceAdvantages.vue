<template>
    <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-4">
      <h2 class="text-2xl font-bold text-gray-200 mb-6">Open Source vs Cloud APIs: Practical Reality</h2>
      
      <div class="overflow-y-auto custom-scrollbar flex-1">
        <div class="grid grid-cols-2 gap-6">
          <div class="bg-gray-900/50 rounded-lg p-6">
            <h3 class="text-xl text-blue-400 mb-4">What Open Source Can Do Better</h3>
            
            <div class="space-y-4">
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Context Length Control</div>
                <div class="text-sm text-gray-300">
                  • Modify context window (8K → 100K)<br/>
                  • Choose model size vs speed trade-off<br/>
                  • Configure memory usage<br/>
                  • Custom chunking strategies<br/>
                  • Example: Process entire documents at once
                </div>
              </div>
              
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Training Flexibility</div>
                <div class="text-sm text-gray-300">
                  • Train on private codebases<br/>
                  • Add company documentation<br/>
                  • Update knowledge cut-off dates<br/>
                  • Custom output formats<br/>
                  • Example: Model knows your API spec
                </div>
              </div>
              
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Inference Control</div>
                <div class="text-sm text-gray-300">
                  • Modify decoding strategies<br/>
                  • Custom batching logic<br/>
                  • Hardware optimization<br/>
                  • Response time guarantees<br/>
                  • Example: 5ms response for search
                </div>
              </div>
  
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Popular Use Cases</div>
                <div class="text-sm text-gray-300">
                  • Code completion engines<br/>
                  • Document search/retrieval<br/>
                  • Real-time chat assistance<br/>
                  • Offline mobile deployment<br/>
                  • High-volume processing
                </div>
              </div>
            </div>
          </div>
  
          <div class="bg-gray-900/50 rounded-lg p-6">
            <h3 class="text-xl text-purple-400 mb-4">What Cloud APIs Do Better</h3>
            
            <div class="space-y-4">
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">Core Capabilities</div>
                <div class="text-sm text-gray-300">
                  • Better reasoning abilities<br/>
                  • Stronger world knowledge<br/>
                  • Multi-modal processing<br/>
                  • More consistent outputs<br/>
                  • Example: Complex analysis tasks
                </div>
              </div>
              
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">Ease of Use</div>
                <div class="text-sm text-gray-300">
                  • Simple API integration<br/>
                  • No model management<br/>
                  • Automatic updates<br/>
                  • Built-in safety features<br/>
                  • Example: Quick prototyping
                </div>
              </div>
              
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">When to Choose APIs</div>
                <div class="text-sm text-gray-300">
                  • Need latest capabilities<br/>
                  • Low-volume processing<br/>
                  • Complex reasoning tasks<br/>
                  • No specialized needs<br/>
                  • Example: General Q&A systems
                </div>
              </div>
  
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">Practical Limitations</div>
                <div class="text-sm text-gray-300">
                  • Fixed context windows<br/>
                  • No custom knowledge<br/>
                  • Rate limiting<br/>
                  • Network dependency<br/>
                  • Higher costs at scale
                </div>
              </div>
            </div>
          </div>
  
          <!-- Bottom Summary -->
          <div class="col-span-2 bg-gray-900/30 p-4 rounded">
            <div class="text-gray-200 font-bold mb-2">Choose Open Source When You Need:</div>
            <div class="text-sm text-gray-300">
              1. Full control over context length and processing<br/>
              2. Integration with private data/knowledge<br/>
              3. Specific performance requirements<br/>
              4. High-volume, cost-effective processing<br/>
              5. Offline or edge deployment
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