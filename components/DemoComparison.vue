<template>
  <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-4">
    <h2 class="text-2xl font-bold text-gray-200 mb-6">Implementation Comparison</h2>
    
    <!-- Added scrollable container -->
    <div class="overflow-y-auto custom-scrollbar flex-1">
      <div class="grid grid-cols-2 gap-6">
        <div class="bg-gray-900/50 rounded-lg p-6 flex flex-col">
          <h3 class="text-xl text-blue-400 mb-4">Open Source Implementation</h3>
          <div class="text-sm text-gray-300 space-y-6">
            <div>
              <div class="font-bold text-blue-300 mb-2">Architecture:</div>
              <ul class="list-disc pl-4 space-y-2">
                <li>Modular System with Multiple Models</li>
                <li>Custom Integration Layer</li>
                <li>Local Processing Pipeline</li>
              </ul>
            </div>
            
            <div>
              <div class="font-bold text-blue-300 mb-2">Technical Stack:</div>
              <ul class="list-disc pl-4 space-y-2">
                <li>PyTorch / TensorFlow Backend</li>
                <li>HuggingFace Transformers</li>
                <li>Custom Caching Layer</li>
                <li>Local Vector Database</li>
                <li>Model Weight Storage</li>
                <li>Training Pipeline</li>
                <li>Data Preprocessing</li>
                <li>Custom Metrics Collection</li>
              </ul>
            </div>
            
            <div>
              <div class="font-bold text-blue-300 mb-2">Infrastructure:</div>
              <ul class="list-disc pl-4 space-y-2">
                <li>High-Performance GPU Servers</li>
                <li>Model Weight Storage (100GB+)</li>
                <li>Load Balancing System</li>
                <li>Monitoring Systems</li>
                <li>Backup Infrastructure</li>
              </ul>
            </div>
          </div>
        </div>

        <div class="bg-gray-900/50 rounded-lg p-6 flex flex-col">
          <h3 class="text-xl text-purple-400 mb-4">Cloud API Implementation</h3>
          <div class="text-sm text-gray-300 space-y-6">
            <div>
              <div class="font-bold text-purple-300 mb-2">Architecture:</div>
              <ul class="list-disc pl-4 space-y-2">
                <li>Unified API Integration</li>
                <li>Serverless Functions</li>
                <li>Cloud-Based Processing</li>
              </ul>
            </div>
            
            <div>
              <div class="font-bold text-purple-300 mb-2">Technical Stack:</div>
              <ul class="list-disc pl-4 space-y-2">
                <li>REST API Endpoints</li>
                <li>Streaming Response Handling</li>
                <li>Cloud Storage Integration</li>
                <li>Managed Services</li>
                <li>API Authentication</li>
                <li>Rate Limiting</li>
                <li>Error Handling</li>
                <li>Response Caching</li>
              </ul>
            </div>
            
            <div>
              <div class="font-bold text-purple-300 mb-2">Infrastructure:</div>
              <ul class="list-disc pl-4 space-y-2">
                <li>API Gateway</li>
                <li>Token Management</li>
                <li>Rate Limiting</li>
                <li>Usage Analytics</li>
                <li>Cost Management</li>
              </ul>
            </div>
          </div>
        </div>
      </div>

      <div class="mt-6 grid grid-cols-2 gap-6">
        <div class="bg-blue-900/20 p-4 rounded">
          <div class="text-blue-400 font-bold mb-2">Development Complexity</div>
          <div class="text-sm text-gray-300">
            Higher initial setup, ongoing maintenance, but complete control over the stack
          </div>
        </div>
        <div class="bg-purple-900/20 p-4 rounded">
          <div class="text-purple-400 font-bold mb-2">Development Speed</div>
          <div class="text-sm text-gray-300">
            Rapid implementation, managed updates, but dependency on provider
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