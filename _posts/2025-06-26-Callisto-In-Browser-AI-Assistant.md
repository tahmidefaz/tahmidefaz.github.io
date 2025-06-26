---
title: "Callisto: A WebGPU based in-browser AI assistant"
date: 2025-06-26 10:10:10 +0500
categories: [Projects, Artificial Intelligence]
tags: [ai]     # TAG names should always be lowercase
---
{%
    include embed/audio.html
    src='/assets/posts/2025-06-26-Callisto-In-Browser-AI-Assistant/audio.wav'
    title='Listen to the article'
%}

I recently had an opportunity to participate in a small hackathon and work on an AI project called Callisto. It's an in-browser conversational AI assistant that leverages the power of WebGPU, making it entirely backend-free and capable of running directly in your browser.

### What is Callisto?

Callisto is a fully in-browser AI assistant that utilizes [WebGPU](https://en.wikipedia.org/wiki/WebGPU) and [ONNX runtime](https://onnxruntime.ai) through the [Transformers.js](https://huggingface.co/docs/transformers.js/en/index) library to run multiple AI models directly in your browser. This means no backend API is required.

![Callisto Screenshot](/assets/posts/2025-06-26-Callisto-In-Browser-AI-Assistant/callisto_screenshot.png)

Your browser **MUST** support **WebGPU** to run Callisto. Please make sure your browser is compatible before proceeding. As of writing this, as long as you are on a Mac running the latest Google Chrome browser, you should be able to run this out of the box. On Linux machines, however, you may need to use a special flag to enable WebGPU on your Chrome. Also, right now, WebGPU support on Firefox is experimental.

### Try It Out

You can check out Callisto by visiting [callisto-lyart.vercel.app](https://callisto-lyart.vercel.app/).

### Improvements Over Previous Work

Callisto builds upon the [webml-community/conversational-webgpu](https://huggingface.co/spaces/webml-community/conversational-webgpu/tree/main) project, adding several new features and enhancements:
- Conversation history.
- Ability to interrupt the assistant during speech.
- Enhanced styling and visuals.

### How Does It Work?

Callisto will download the following 4 different AI models, and then run everything inside your browser.

1. Large Language Model ([HuggingFaceTB/SmolLM2-1.7B-Instruct](https://huggingface.co/HuggingFaceTB/SmolLM2-1.7B-Instruct))
2. Speech to text ([onnx-community/whisper-base](https://huggingface.co/onnx-community/whisper-base))
3. Text to speech ([onnx-community/Kokoro-82M-v1.0-ONNX](https://huggingface.co/onnx-community/Kokoro-82M-v1.0-ONNX))
4. Voice detection model ([onnx-community/silero-vad](https://huggingface.co/onnx-community/silero-vad))

Depending on your internet connection, it might take a few minutes to load everything the first time. Second time onward, however, it will load much faster because of caching.

### Running Locally

If you want to run Callisto locally, follow these simple steps:
1. Clone [this repository](https://github.com/tahmidefaz/callisto).
2. Run `npm install`.
3. Execute `npm run dev`.

That's it! You'll have Callisto running on your machine.
