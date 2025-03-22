# Audio Transcription and Text-to-Speech (TTS) System

## Project Overview
This project demonstrates an integrated pipeline for audio transcription and text-to-speech (TTS) synthesis. It combines multiple state-of-the-art models and libraries to process audio files, transcribe them into text, and generate synthetic speech from the processed text. The system also includes Voice Activity Detection (VAD) for filtering noise and non-speech segments.

---

## Features

### 1. Audio Format Conversion
- Converts audio files (M4A, MP3) to WAV format with the required specifications (32kHz sample rate, mono).

### 2. Voice Activity Detection (VAD)
- Filters out non-speech audio segments using `webrtcvad`.

### 3. Audio Transcription
- Utilizes the `faster-whisper` model to transcribe filtered audio into text.

### 4. Text Processing
- Processes the transcribed text to generate concise responses using the LLaMA language model.

### 5. Text-to-Speech (TTS)
- Converts processed text into synthetic speech using Microsoft's `SpeechT5` model and HiFi-GAN vocoder.

### 6. Tunable Parameters
- Allows customization of voice pitch, speed, gender, and VAD threshold.

---

## Purpose
The primary goal of this project is to create a seamless workflow for:
1. Transcribing spoken content into text with high accuracy.
2. Generating natural and customizable synthetic speech from text descriptions or prompts.

This system can be used in various applications, such as content creation, accessibility tools, virtual assistants, and more.

---

## Technologies Used

### Libraries
- `webrtcvad`: For Voice Activity Detection.
- `pydub`: For audio format conversion and manipulation.
- `faster-whisper`: A lightweight Whisper model for transcription.
- `transformers`: To leverage the LLaMA language model and Microsoft's SpeechT5 model.
- `soundfile` and `torchaudio`: For audio processing.
- `datasets`: For loading speaker embeddings.

### Models
- **Whisper model** (`faster-whisper`) for transcription.
- **LLaMA language model** for text generation.
- **SpeechT5** and **HiFi-GAN** for text-to-speech synthesis.

---

## Workflow

### 1. Audio Input
- Provide an audio file in M4A or MP3 format.
- The file is converted to WAV format with the required specifications.

### 2. Voice Activity Detection
- The WAV file undergoes VAD filtering to remove non-speech segments.

### 3. Transcription
- Filtered audio is transcribed into text using the Whisper model.

### 4. Text Processing
- The transcribed text is processed by the LLaMA language model to generate concise responses.

### 5. Text-to-Speech Synthesis
- The processed text is synthesized into speech using SpeechT5 and HiFi-GAN.
- The resulting audio file is saved in WAV format.

---

## Outcomes
- Accurate transcription of audio files into text.
- Natural and customizable synthetic speech generation.
- Integration of VAD ensures clean and concise audio processing.

---

## Usage Instructions

1. Clone the repository and install the required libraries:
   ```bash
   pip install webrtcvad pydub faster-whisper transformers torch torchaudio soundfile datasets accelerate sentencepiece opencv-python


