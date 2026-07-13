# Ai-voice-Assistant

A simple voice assistant you can talk to — it listens, thinks, and talks back.
Speak into your mic, and it replies out loud like a real assistant.

## What it does

1. You speak into the microphone.
2. It converts your speech to text (using OpenAI's Whisper).
3. It sends that text to an AI model (Groq's Llama 3.3 70B) to generate a reply.
4. It converts the AI's reply back into speech (using Edge TTS).
5. You hear the assistant talk back — all through a simple web interface.

## Tech stack

- **Whisper** – speech-to-text
- **Groq API (Llama 3.3 70B)** – the "brain" that generates responses
- **Edge TTS** – text-to-speech
- **Gradio** – the web UI, so you can just talk into your browser mic

## Getting started

### 1. Clone the repo
```bash
git clone https://github.com/<your-username>/<repo-name>.git
cd <repo-name>
```

### 2. Install the requirements
```bash
pip install -r requirements.txt
```

### 3. Add your Groq API key
Get a free key from [Groq](https://console.groq.com), then set it as an
environment variable — never hardcode it in the code:


### 4. Run it
```bash
python app.py
```

Gradio will open a local link (and optionally a public share link) in your
browser. Click the mic, speak, and wait for the reply.

## How it's built

The whole thing started as a single Jupyter/Colab notebook
(`voice_assistant.ipynb`) where each piece — speech-to-text, the AI chat
call, text-to-speech — was built and tested step by step before wrapping it
all into one `voice_assistant()` function and hooking it up to a Gradio
interface.

## Notes

- First run downloads the Whisper model, so it might take a minute to load.
- Response speed depends on your internet connection, since both Groq and
  Edge TTS are cloud services.
- This is a demo/learning project, not production-hardened — no error
  handling for things like empty audio or API rate limits yet.
