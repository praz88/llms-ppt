<template>
    <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-4">
      <h2 class="text-2xl font-bold text-gray-200 mb-6">Cost Analysis: Open Source vs Cloud API</h2>
      
      <div class="overflow-y-auto custom-scrollbar flex-1">
        <div class="grid grid-cols-2 gap-6">
          <div class="bg-gray-900/50 rounded-lg p-6">
            <h3 class="text-xl text-blue-400 mb-4">Open Source on Cloud</h3>
            
            <div class="space-y-4">
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Cloud Infrastructure (AWS/GCP)</div>
                <div class="text-sm text-gray-300">
                  • GPU Instances (A100): ₹800-1200/hour<br/>
                  • Storage (500GB SSD): ₹4K-6K/month<br/>
                  • Data Transfer: ₹8/GB<br/>
                  • Load Balancer: ₹4K-6K/month<br/>
                  • Monitoring: ₹2K-4K/month
                </div>
              </div>
              
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Monthly Usage Examples</div>
                <div class="text-sm text-gray-300">
                  • Small Scale (8hrs/day):<br/>
                    - GPU Costs: ₹2L/month<br/>
                    - Infrastructure: ₹20K/month<br/>
                  • Medium Scale (16hrs/day):<br/>
                    - GPU Costs: ₹4L/month<br/>
                    - Infrastructure: ₹40K/month<br/>
                  • Large Scale (24/7):<br/>
                    - GPU Costs: ₹8L/month<br/>
                    - Infrastructure: ₹80K/month
                </div>
              </div>
              
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Development Team</div>
                <div class="text-sm text-gray-300">
                  • MLOps Engineer: ₹2L-3L/month<br/>
                  • ML Engineer: ₹1.5L-2.5L/month<br/>
                  • DevOps Support: ₹1L-2L/month<br/>
                  • Training & Updates: ₹50K/month<br/>
                  • Documentation: ₹30K/month
                </div>
              </div>
  
              <div class="bg-blue-900/20 p-4 rounded">
                <div class="font-bold text-blue-300 mb-2">Hidden Costs</div>
                <div class="text-sm text-gray-300">
                  • Model Retraining<br/>
                  • Performance Optimization<br/>
                  • Security Updates<br/>
                  • API Gateway Management<br/>
                  • Backup & Recovery
                </div>
              </div>
            </div>
          </div>
          
          <div class="bg-gray-900/50 rounded-lg p-6">
            <h3 class="text-xl text-purple-400 mb-4">Cloud API Services</h3>
            
            <div class="space-y-4">
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">API Usage Costs</div>
                <div class="text-sm text-gray-300">
                  • Input: ₹0.80/1K tokens (~750 words)<br/>
                  • Output: ₹2.40/1K tokens (~750 words)<br/>
                  • Image Processing: ₹0.80/image<br/>
                  • Batch Processing: ₹0.64/1K tokens<br/>
                  • Fine-tuning: ₹2.40/1K tokens
                </div>
              </div>
              
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">Monthly Usage Examples</div>
                <div class="text-sm text-gray-300">
                  • Small Scale (100K words):<br/>
                    - Input: ₹107/month<br/>
                    - Output: ₹320/month<br/>
                  • Medium Scale (1M words):<br/>
                    - Input: ₹1,070/month<br/>
                    - Output: ₹3,200/month<br/>
                  • Large Scale (10M words):<br/>
                    - Input: ₹10,700/month<br/>
                    - Output: ₹32,000/month
                </div>
              </div>
              
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">Infrastructure Costs</div>
                <div class="text-sm text-gray-300">
                  • API Gateway: ₹8K-16K/month<br/>
                  • Response Caching: ₹4K-8K/month<br/>
                  • Error Monitoring: ₹4K-8K/month<br/>
                  • Analytics: ₹4K-8K/month<br/>
                  • Rate Limiting: Built-in
                </div>
              </div>
  
              <div class="bg-purple-900/20 p-4 rounded">
                <div class="font-bold text-purple-300 mb-2">Development Team</div>
                <div class="text-sm text-gray-300">
                  • Backend Engineer: ₹1.5L-2L/month<br/>
                  • API Integration: ₹4L-6L (one-time)<br/>
                  • Documentation: ₹1L-2L (one-time)<br/>
                  • Support: ₹50K-80K/month
                </div>
              </div>
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