<script setup>
import { onMounted } from 'vue'
import gsap from 'gsap'

onMounted(() => {
  gsap.from('.slide-title', {
    y: -20,
    opacity: 0,
    duration: 0.6
  })

  gsap.from('.code-panel-left', {
    x: -40,
    opacity: 0,
    duration: 0.8,
    delay: 0.3
  })

  gsap.from('.code-panel-right', {
    x: 40,
    opacity: 0,
    duration: 0.8,
    delay: 0.3
  })

  gsap.from('.feature-item', {
    y: 20,
    opacity: 0,
    duration: 0.4,
    stagger: 0.1,
    delay: 0.8
  })
})
</script>

<template>
  <div class="h-full w-full overflow-hidden bg-[#0A1120] flex flex-col p-4">
    <h2 class="text-2xl font-bold text-gray-200 mb-4 slide-title">Advanced Capabilities</h2>
    
    <div class="grid grid-cols-2 gap-4 flex-1 overflow-hidden">
      <!-- Open Source Panel -->
      <div class="code-panel-left bg-gray-900/50 rounded-lg p-4 flex flex-col overflow-hidden">
        <h3 class="text-xl text-blue-400 mb-3">Vision + Understanding</h3>
        <div class="font-mono text-sm text-gray-300 overflow-y-auto flex-1 custom-scrollbar">
          <pre class="whitespace-pre">
from transformers import pipeline
import torch

def analyze_image_and_respond(
    image_path: str,
    prompt: str
) -> dict:
    # Load CLIP for image understanding
    vision_model = pipeline(
        "image-to-text",
        model="openai/clip-vit-base-patch32",
        device="cuda" if torch.cuda.is_available() else "cpu"
    )
    
    # Load Llama for text generation
    llm = pipeline(
        "text-generation",
        model="meta-llama/Llama-2-70b-chat-hf",
        device="cuda"
    )
    
    # Get image description
    image_desc = vision_model(image_path)
    
    # Generate response
    context = f"""
    Image description: {image_desc}
    User question: {prompt}
    """
    
    response = llm(context)
    
    return {
        "description": image_desc,
        "response": response
    }</pre>
        </div>
        <div class="mt-4 text-sm text-gray-400">
          <div class="feature-item">✗ Separate models needed</div>
          <div class="feature-item">✗ Manual integration</div>
          <div class="feature-item">✗ Higher compute required</div>
          <div class="feature-item">✗ Complex deployment</div>
        </div>
      </div>

      <!-- Big Tech Panel -->
      <div class="code-panel-right bg-gray-900/50 rounded-lg p-4 flex flex-col overflow-hidden">
        <h3 class="text-xl text-purple-400 mb-3">Unified Multimodal + Functions</h3>
        <div class="font-mono text-sm text-gray-300 overflow-y-auto flex-1 custom-scrollbar">
          <pre class="whitespace-pre">
from openai import OpenAI
import json

def analyze_with_gpt4v(
    image_path: str,
    prompt: str,
    tools: list
) -> dict:
    client = OpenAI()
    
    # Define analysis function
    analyze_tool = {
        "type": "function",
        "function": {
            "name": "analyze_data",
            "description": "Analyze data from image",
            "parameters": {
                "type": "object",
                "properties": {
                    "metrics": {
                        "type": "array",
                        "items": {"type": "string"}
                    },
                    "insights": {
                        "type": "array",
                        "items": {"type": "string"}
                    }
                }
            }
        }
    }

    response = client.chat.completions.create(
        model="gpt-4-vision-preview",
        messages=[
            {
                "role": "user",
                "content": [
                    {
                        "type": "text",
                        "text": prompt
                    },
                    {
                        "type": "image_url",
                        "image_url": image_path
                    }
                ]
            }
        ],
        tools=[analyze_tool, *tools],
        tool_choice="auto"
    )
    
    return {
        "analysis": response.choices[0].message,
        "tool_calls": response.choices[0].tool_calls,
        "usage": response.usage
    }</pre>
        </div>
        <div class="mt-4 text-sm text-gray-400">
          <div class="feature-item">✓ Single API call</div>
          <div class="feature-item">✓ Built-in tool calls</div>
          <div class="feature-item">✓ Automatic function routing</div>
          <div class="feature-item">✓ Managed infrastructure</div>
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