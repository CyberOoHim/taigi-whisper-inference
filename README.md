# 🗣️ Taigi Whisper Inference

> [!CAUTION]
> **EXPERIMENTAL STATUS:** The Taigi POJ ASR model used in this notebook is currently in an experimental phase and is considered immature. Accuracy and performance may vary significantly depending on the input audio.

This repository provides a high-performance, interactive inference solution for Taigi (Taiwanese) speech recognition. It leverages **Faster-Whisper** and **CTranslate2** for lightning-fast transcription and features a comprehensive **Gradio** web interface.

## 🚀 Quick Start: Google Colab

The easiest way to try out the model is through our interactive notebook in Google Colab.

### 📓 Taigi Whisper Inference Notebook

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/CyberOohim/taigi-whisper-inference/blob/main/gradio_inference_fast_whisper_time_code.ipynb)

### ⚠️ Important Before Running (Google Colab)

1. **Enable T4 GPU:**
   - Click on **Runtime** in the top menu bar.
   - Select **Change runtime type** from the dropdown.
   - Under **Hardware accelerator**, choose **T4 GPU** and click **Save**.
   - *Tip:* You can verify the GPU is connected by running `!nvidia-smi` in a code cell; you should see "Tesla T4" in the output.
2. **Hugging Face Token (Optional):**
   - To accelerate model downloading and avoid rate limits, it is recommended to add your `HF_TOKEN` to your Colab Secrets (the 🔑 icon in the left sidebar).

---

## ✨ Core Features

### ⚡ High-Performance Inference

- **Faster-Whisper & CT2:** Powered by CTranslate2 for up to 4x speed increases over standard Whisper.
- **Model Flexibility:** Supports native CT2 models, standard Hugging Face models, and on-the-fly PEFT/LoRA adapter merging.
- **Quantization:** Support for `float16` (GPU) and `int8` (CPU) to optimize for your specific hardware.

### 🌐 Interactive Gradio Web UI

- **Dual Input:** Record directly from your microphone or upload audio files (MP3, WAV, FLAC, etc.).
- **VAD (Voice Activity Detection):** Integrated VAD to filter out silence and background noise automatically.
- **Accessibility:** Large font sizes (45px) optimized for reading complex Taigi diacritics.
- **One-Click Copy:** Convenient buttons to copy transcriptions directly to your clipboard.

### 🇹🇼 Taigi-Specific Optimizations

- **POJ Converter:** Automatic conversion from numeric POJ (e.g., `ta5-gi2`) to standard diacritics (e.g., `tâi-gí`).
- **Dual Output:** Displays both raw model output and converted POJ text side-by-side.
- **SRT Generation:** Export subtitles in SRT format with customizable timestamp granularity (Segment-level or Word-level).

### 🤖 Environment Intelligence

The notebook automatically detects whether it's running in **Google Colab**, **Kaggle**, or a **Local** environment and adjusts its configuration accordingly.

---

## 🛠️ Local Installation

To run this project on your own machine:

1. **Clone the repository:**

   ```bash
   git clone https://github.com/CyberOohim/taigi-whisper-inference.git
   cd taigi-whisper-inference
   ```

2. **Set up a Virtual Environment (Recommended):**

   ```bash
   python -m venv venv
   # Windows:
   .\venv\Scripts\activate
   # Linux/Mac:
   source venv/bin/activate
   ```

3. **Install Dependencies:**

   ```bash
   pip install -r requirements.txt
   ```

4. **Configuration:**
   Rename `.env.example` to `.env` and add your Hugging Face token:

   ```bash
   HF_TOKEN=your_token_here
   ```

5. **Run the Notebook:**
   Open `gradio_inference_fast_whisper_time_code.ipynb` using VS Code, Jupyter Lab, or Jupyter Notebook.

---

## 📖 User Guide

1. **Initialization:** Run the first cell to install dependencies and configure the environment.
2. **Model Loading:** Provide a path or Hugging Face repo ID for the `faster-whisper` model.
3. **Interface Launch:** Execute the Gradio cell to start the web UI.
4. **Transcription:**
   - Record or Upload audio.
   - Adjust VAD settings if needed.
   - Click **Transcribe**.
5. **Export:** Download the generated SRT file or copy the text using the provided buttons.

---

## 📜 License

### MIT License

Copyright (c) 2024-2026 Taigi Whisper Inference Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
