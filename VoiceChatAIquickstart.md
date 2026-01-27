# Voice Chat AI quickstart

## Startup

first make sure these programs are running

- start `docker desktop`
- start `ollama`

then execute these commands in powershell
```
docker run -d --name kokoro-tts -p 8880:8880 ghcr.io/remsky/kokoro-fastapi-cpu:latest
#or if the docker already exists
docker start kokoro-tts

venv\Scripts\activate
cd .\voice-chat-ai\
python -m uvicorn app.main:app --host 0.0.0.0 --port 8000
```

finally to access the GUI open this in your browser
```
http://127.0.0.1:8000/
```

## Initial setup

before starting dont forget to select the right settings in the webgui

- for `Model Provider` select `Ollama`
- for `TTS Provider` select `Kokoro-TTS`
- for `Ollama Model` select the model you want to use
- and for `Transcription` select `Local Faster Whisper`

## Shutdown

`ctrl c` in the correct terminal to exit `Voice Chat Ai`

to stop Kokoro execute the following command in any terminal 
```
docker stop kokoro-tts
```
exit `docker desktop` and `ollama` through the system tray or task manager
