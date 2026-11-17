# Smart Home AI Access System

A smart-home door access system. It recognizes faces, listens to voice commands, and uses an AI agent to decide who may enter.

## Features

- **AI agent (LangChain + LLaMA 3 via Ollama)**
  - Talks to guests at the door.
  - Understands the owner's voice commands.
- **Face recognition (OpenCV + face_recognition)**
  - Identifies people by their face.
  - Logs unknown visitors.
- **Voice control**
  - The owner can say "This is my friend" and the AI grants access.
  - Supported commands: `add`, `open`, `deny`, and more.
- **Access log (audit)**
  - Who tried to enter, when, and how.
  - Which command was given and who was allowed in.

## Tech stack

| Technology | Purpose |
|---|---|
| FastAPI | Backend REST API |
| OpenCV | Face detection |
| face_recognition | Face matching |
| LangChain | Build the AI agent |
| LLaMA 3 (Ollama) | Local LLM for natural language |
| SQLite / PostgreSQL | Database |
| Pydantic | Data schemas |
| JWT | Token-based authentication |

## Setup

```bash
git clone https://github.com/dastonbek8747/smart-home-face-access.git
cd smart-home-face-access

python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate

pip install -r app/requirements.txt

cp .env.example .env            # then edit .env
```

## Run

```bash
uvicorn app.main:app --reload
```

API docs: http://localhost:8000/docs

## Project structure

```
app/
  api/routers/     # auth, face, guests, logs, voice endpoints
  core/            # config and security helpers
  database/        # session and base models
  models/          # user, guest, log tables
  schemas/         # request/response schemas
  services/        # ai_agent, face_recognition, voice_handler, logger, notify
  main.py          # app entry point
```

## License

MIT
