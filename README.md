# AI-Voice-Assistance

# End-to-End AI Voice Assistant

## Overview
This project implements an end-to-end AI voice assistant capable of:
1. Converting spoken audio into text (**Voice-to-Text**).
2. Generating a response using a **Large Language Model (LLM)**.
3. Converting the generated text back into speech (**Text-to-Speech**).

The workflow is divided into three main steps: **Voice-to-Text Conversion**, **Text Input into LLM**, and **Text-to-Speech Conversion**.

---

## Features

### 1. Voice-to-Text Conversion (Using Whisper)
- **Libraries Used**:
  - `wave`: To read and process WAV audio files.
  - `webrtcvad`: For Voice Activity Detection (VAD) to filter non-speech portions.
  - `pydub`: For audio file conversion and manipulation (e.g., M4A or MP3 to WAV).
  - `faster-whisper`: Efficient implementation of the Whisper model for transcription.
- **Implementation**:
  - **Audio Conversion**: Converts M4A/MP3 files to WAV format at 32 kHz mono channel.
  - **VAD Filtering**: Removes non-speech frames using WebRTC VAD for noise reduction.
  - **Transcription**: Uses the Whisper model to convert filtered audio into text.
- **Advantages**:
  - **Efficiency**: Real-time transcription with faster-whisper.
  - **Accuracy**: Improved transcription quality with VAD.

---

### 2. Text Input into LLM (Using LLaMA)
- **Libraries Used**:
  - `torch`: For tensor computation and GPU acceleration.
  - `transformers`: For loading and interacting with pre-trained models.
- **Implementation**:
  - **Model Loading**: LLaMA is loaded using Hugging Face's `AutoTokenizer` and `AutoModelForCausalLM`.
  - **Tokenization & Inference**: Tokenizes transcribed text and generates responses with customizable parameters (e.g., `top_k`, `top_p`, `temperature`).
  - **Response Processing**: Cleans generated output for conciseness.
- **Advantages**:
  - **Customizability**: Fine-tuning generation parameters for creative and relevant responses.
  - **Scalability**: GPU support for real-time applications.

---

### 3. Text-to-Speech Conversion (Using Parler TTS)
- **Libraries Used**:
  - `parler-tts`: For speech synthesis from text.
  - `soundfile`: For handling audio file operations.
- **Implementation**:
  - **Limiting Sentences**: Ensures concise output for synthesized speech.
  - **VAD Application**: Filters low-energy segments for clarity.
  - **Text-to-Speech Conversion**: Converts text into speech with adjustable parameters (pitch, speed, gender).
- **Advantages**:
  - **Flexibility**: Customizable speech characteristics for user preferences.
  - **Clarity**: Ensures only relevant segments are synthesized.

---

## Models Used
1. **Whisper (faster-whisper)**: Optimized for fast and accurate speech-to-text transcription.
2. **LLaMA (open_llama_3b)**: Generates contextually relevant and coherent text responses.
3. **Parler TTS**: Produces high-quality, natural-sounding speech with adjustable parameters.

---

## Technologies Used
- **Libraries**: `faster-whisper`, `torch`, `transformers`, `pydub`, `webrtcvad`, `soundfile`, `parler-tts`.
- **Models**: Whisper, LLaMA, Parler TTS.

---

## Conclusion
This AI voice assistant pipeline integrates cutting-edge models for **speech transcription**, **language understanding**, and **speech synthesis**, providing an efficient and flexible solution for voice-based applications. Features like **VAD**, **model optimization**, and **customizable parameters** ensure high-quality outputs tailored to diverse use cases.

