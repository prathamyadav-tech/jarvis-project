# JARVIS Starter — Step 1: Text Brain (Ollama / Free / Local)

This runs entirely on your own machine using Ollama — no API key, no cost,
no internet needed once set up.

## Setup

1. Install Ollama from https://ollama.com (Windows/Mac/Linux).
2. Open a terminal and pull a model (one-time download):
   ```
   ollama pull llama3.1
   ```
   If your laptop has limited RAM (under 8GB), use a smaller model instead:
   ```
   ollama pull llama3.2:1b
   ```
   and update `MODEL_NAME` in `jarvis.py` to match.
3. Install the one Python dependency:
   ```
   pip install -r requirements.txt
   ```
4. Run it:
   ```
   python jarvis.py
   ```

Ollama usually runs automatically in the background after install. If you
get a connection error, open a separate terminal and run `ollama serve`,
then try again.

## Notes

- Local models are noticeably less capable than Claude/GPT-4-class models,
  especially at reasoning and following complex instructions. For a
  hackathon demo this is usually fine — just keep the tasks you ask it to
  do fairly simple and concrete.
- If responses feel too slow, try a smaller/quantized model
  (e.g. `llama3.2:1b` or `phi3`) — smaller models run faster on modest hardware.

## What's next

1. **Speech-to-text**: swap `input()` for a function that records your mic
   and transcribes it (try `SpeechRecognition` or `openai-whisper` — Whisper
   also runs fully locally and free).
2. **Text-to-speech**: pipe `reply` through `pyttsx3` (fully offline) so
   JARVIS talks back instead of printing.
3. **Wake word**: add `pvporcupine` (has a free tier) so it only starts
   listening when you say "Hey Jarvis".
4. **Tools/actions**: some Ollama models support function calling — ask me
   when you're ready and I'll show you how to wire that up.

Come back and ask for code for any of these next steps whenever you're ready.