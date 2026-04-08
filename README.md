# 🎓 HCMUS Computational Thinking Chatbot

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ThayLoser/ollama-gradio-colab/blob/main/GradioOllamaVietnamese.ipynb)
[![Python Version](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)

A web-based AI chatbot application designed to act as a Computational Thinking (Tư duy tính toán) lecturer for the University of Science, VNU-HCM. This project runs entirely within Google Colab, utilizing **Ollama** to serve the model locally and **Gradio** to provide an interactive, multimodal web interface.

<img width="1918" height="863" alt="Screenshot 2026-04-08 081003" src="https://github.com/user-attachments/assets/848c2735-b22c-4a66-850c-218f28abfc31" />

## 👨‍💻 Student Information
* **Full Name:** Nguyễn Anh Thái
* **Student ID:** 24120224
* **Course:** Tư duy tính toán (Computational Thinking)
* **Group:** CQ2024/2 [N1]

## ✨ Features

* **Custom Academic Persona:** The LLM is strictly prompted to respond as a university lecturer, providing tailored, educational assistance.
* **Multimodal Support:** Users can upload images alongside their text prompts, taking full advantage of Gemma 3's vision capabilities.
* **Typewriter Streaming Effect:** Responses are yielded word-by-word with a slight delay (`0.05s`) to simulate real-time typing and improve user experience.
* **100% Free Cloud Execution:** Uses background threading to run the Ollama Linux server natively inside a Google Colab instance alongside the UI.
* **Information Sidebar:** Built-in Gradio accordions displaying project metadata and detailed information about the underlying model.

## 🧠 Powered by Gemma 3

This application utilizes **`gemma3:4b`**, pulled directly via Ollama. 
Gemma is a family of lightweight, state-of-the-art open models from Google, built from the same research and technology used to create the Gemini models. The 4B parameter version is exceptionally efficient, offering a 128K context window and the ability to process both text and images seamlessly.

## 🚀 How to Run in Google Colab

1. **Open the Notebook:** Click the "Open in Colab" badge at the top of this repository.
2. **Enable GPU:** For optimal generation speeds, go to `Runtime` > `Change runtime type` and select a **T4 GPU** hardware accelerator.
3. **Execute the Code:** Run the cells sequentially (or press `Ctrl+F9` to run all). The code will automatically:
   * Install necessary system packages (`zstd`, `pciutils`).
   * Download and install Ollama.
   * Start the Ollama server in a background thread.
   * Pull the `gemma3:4b` model weights.
   * Install `gradio` and launch the web interface.
4. **Chat:** Once the final cell finishes, click the public `https://xxxxxx.gradio.live` link generated at the bottom to open your chatbot in a new tab.

## 📁 Project Structure

The single Colab notebook handles everything from environment setup to deployment:
* **Cell 1:** System dependencies and Ollama installation.
* **Cell 2:** Background threading setup (`subprocess.Popen`) to keep the Ollama server running.
* **Cell 3:** Model weight retrieval (`ollama pull`).
* **Cell 4:** Python library installations (`pip install`).
* **Cell 5:** Core application logic, including the `chatbotResponse` function, history management, and Gradio UI rendering.
