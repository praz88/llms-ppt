<template>
    <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-4">
      <h2 class="text-2xl font-bold text-gray-200 mb-4">Smart Features: Open Source vs Big Tech</h2>
      
      <div class="grid grid-cols-2 gap-4 flex-1 overflow-hidden">
        <!-- Open Source -->
        <div class="bg-gray-900/50 rounded-lg p-4 flex flex-col overflow-hidden">
          <h3 class="text-xl text-blue-400 mb-3">Open Source (Mistral 7B)</h3>
          <div class="font-mono text-sm text-gray-300 overflow-y-auto flex-1 custom-scrollbar">
            <pre class="whitespace-pre">
  from transformers import pipeline
  
  def generate_response(prompt: str) -> str:
      # Basic chat completion
      model = pipeline(
          "text-generation",
          model="mistralai/Mistral-7B-v0.1",
          device="cuda"
      )
      
      response = model(
          prompt,
          max_length=128,
          temperature=0.7,
          num_return_sequences=1
      )[0]['generated_text']
      
      return response.strip()
  
  # Usage
  result = generate_response(
      "What are the benefits of exercise?"
  )
  print(result)
  
  # Output:
  # Exercise has numerous benefits including:
  # - Improved cardiovascular health
  # - Increased strength and endurance
  # - Better mental wellbeing</pre>
          </div>
          <div class="mt-4 text-sm text-gray-400">
            ✓ Full model control<br>
            ✓ Local deployment<br>
            ✓ Customizable parameters<br>
            ✗ Limited context window<br>
            ✗ Basic completion only
          </div>
        </div>
  
        <!-- Big Tech -->
        <div class="bg-gray-900/50 rounded-lg p-4 flex flex-col overflow-hidden">
          <h3 class="text-xl text-purple-400 mb-3">Big Tech (Claude API)</h3>
          <div class="font-mono text-sm text-gray-300 overflow-y-auto flex-1 custom-scrollbar">
            <pre class="whitespace-pre">
  from anthropic import Anthropic
  
  def generate_response(prompt: str) -> dict:
      """Generate an AI response with advanced features."""
      
      client = Anthropic(api_key="your_key")
      
      # Advanced multi-tool response
      messages = [
          {
              "role": "user",
              "content": [
                  {
                      "type": "text",
                      "text": prompt
                  },
                  {
                      "type": "image",
                      "source": {
                          "type": "base64",
                          "media_type": "image/jpeg",
                          "data": "..."
                      }
                  }
              ]
          }
      ]
      
      response = client.messages.create(
          model="claude-3-opus-20240229",
          max_tokens=1024,
          temperature=0.7,
          messages=messages,
          system="You are an AI assistant that...",
      )
      
      return {
          "text": response.content[0].text,
          "analysis": response.content[0].metadata,
          "citations": response.citations,
          "tool_calls": response.tool_calls
      }
  
  # Usage
  result = generate_response(
      "Analyze this image and explain the health benefits of the exercise shown."
  )
  print(f"Analysis: {result['analysis']}")
  print(f"Citations: {result['citations']}")
  </pre>
          </div>
          <div class="mt-4 text-sm text-gray-400">
            ✓ Multi-modal input (text + images)<br>
            ✓ Advanced features (analysis, citations)<br>
            ✓ System prompts & tool calls<br>
            ✓ Larger context window<br>
            ✓ Structured outputs
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <style>
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