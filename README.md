# 📁 Virtual Uyga Kirish Tizimi — FastAPI Backend Loyihasi

# 🧱 Loyihaning Tuzilishi

project/
├── app/
│   ├── api/                 # FastAPI endpoint router'lari
│   │   ├── routes/
│   │   │   ├── auth.py      # Kirish/ro'yxatdan o'tish
│   │   │   ├── access.py    # Kirish ruxsati (Face API)
│   │   │   └── user.py      # Foydalanuvchi bilan bog'liq endpointlar
│   │   └── deps.py          # Token tekshiruv, roli tekshirish
│   ├── core/
│   │   ├── config.py        # Sozlamalar (env)
│   │   └── security.py      # JWT va xavfsizlik
│   ├── models/              # SQLAlchemy ORM modellar
│   │   ├── user.py
│   │   └── log.py           # Kirish loglari (kim, qachon kirgan)
│   ├── schemas/             # Pydantic sxemalar
│   │   ├── user.py
│   │   └── access.py
│   ├── services/            # Business logika
│   │   ├── face.py          # OpenCV bilan ishlovchi modul
│   │   ├── ai_agent.py      # LangChain + LLaMA3 agent xulosa beradi
│   │   └── notify.py        # Telegram yoki email xabarnoma
│   ├── database.py          # DB ulanishi
│   └── main.py              # FastAPI ilovasi
├── .env                     # Maxfiy sozlamalar (LLM API, JWT key, DB url)
├── requirements.txt
└── README.md

# ✅ Bosqichma-bosqich Yozilishi

## 1. API boshlanishi — FastAPI + Auth + DB
- [ ] JWT asosida kirish va ro'yxatdan o'tish
- [ ] Foydalanuvchini qo'shish (admin)
- [ ] Kirgan foydalanuvchini logga yozish

## 2. Face tanib olish API (OpenCV)
- [ ] Kamera orqali rasm olish (base64 yoki fayl sifatida)
- [ ] Rasmni tahlil qilish: yuz bor/yo‘qligini aniqlash
- [ ] Tanilgan bo‘lsa, AI agentdan ruxsat so‘rash (LangChain)

## 3. AI agent (LangChain + LLaMA3 via Ollama)
- [ ] Foydalanuvchi haqida ma’lumot yuborish
- [ ] Agent: "Ushbu foydalanuvchiga ruxsat berilsinmi?"
- [ ] Agent izoh bilan javob beradi (LangGraph da flow)

## 4. Xabarnoma
- [ ] Admin telegram botga xabar: "Anvar kirishga harakat qildi"
- [ ] Ruxsat berildi yoki rad etildi degan izoh

## 5. Frontend (alohida loyiha)
- [ ] Vue 3 yoki Telegram bot orqali ishlash (tanlanadi)

## 📦 `requirements.txt` (asosiy kutubxonalar)
```
fastapi
uvicorn
python-multipart
pydantic
sqlalchemy
databases
passlib[bcrypt]
python-jose
opencv-python
langchain
ollama
langgraph
requests
python-telegram-bot
```

## 📘 `README.md` qisqacha ko'rinishi
```
# 🏠 AI Face Access System

AI yordamida foydalanuvchilarni yuz orqali tanib, ularning kirishiga ruxsat beruvchi tizim. Ruxsat AI agent tomonidan aniqlanadi (LangChain + LLaMA3).

## Texnologiyalar
- FastAPI, OpenCV, LangChain, LLaMA3, Ollama, PostgreSQL, Telegram API

## Boshlash uchun:
```bash
cp .env.example .env
uvicorn app.main:app --reload
```

## API endpointlar:
- POST /auth/login
- POST /auth/register
- POST /access/detect_face
- GET /access/logs
```

---

Hozir API yozishni boshlashga tayyormiz. Avval `main.py`, `database.py`, `config.py`, `auth.py` va `user.py` qismlarini yozamizmi? Yoki `face.py`dan boshlaymizmi?

❓ Qaysi modulli API'dan boshlaylik: `auth`, `face`, yoki `agent`?
