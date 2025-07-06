# 📁 Virtual Uyga Kirish Tizimi — FastAPI Backend Loyihasi

# 🧱 Loyihaning Tuzilishi

smart_home_access/
├── app/
│   ├── main.py                 # FastAPI kirish nuqtasi
│   ├── core/                   # Sozlamalar va konfiglar
│   │   ├── config.py           # Loyihaning umumiy sozlamalari
│   │   └── security.py         # Token, autentifikatsiya funksiyalari
│   ├── models/                 # SQLAlchemy ORM modellari
│   │   ├── user.py             # Uy egasi va foydalanuvchilar
│   │   ├── log.py              # Loglar (kirish, buyruqlar)
│   │   ├── guest.py            # Mehmonlar modeli
│   ├── schemas/                # Pydantic validatsiya sxemalari
│   │   ├── user.py
│   │   ├── log.py
│   │   ├── guest.py
│   ├── api/                    # Routerlar
│   │   ├── deps.py             # Bog'lanishlar
│   │   └── routes/
│   │       ├── auth.py         # Login / JWT
│   │       ├── face.py         # Yuz tanib olish
│   │       ├── voice.py        # Ovozli buyruqlar
│   │       ├── logs.py         # Loglarni ko‘rish
│   │       └── guests.py       # Mehmonlar qo‘shish, olib tashlash
│   ├── services/               # Asosiy xizmatlar (logika)
│   │   ├── ai_agent.py         # LangChain/LLaMA agent
│   │   ├── face_recognition.py # OpenCV + Face tanish
│   │   ├── voice_handler.py    # Ovozli buyruqni tanib olish
│   │   ├── logger.py           # Log yozish servisi
│   │   └── notify.py           # Telegram/e-mail yuborish
│   ├── database/
│   │   ├── base.py             # Baza ulanishi
│   │   └── session.py
├── requirements.txt            # Kutubxonalar ro‘yxati
├── README.md                   # Loyihaning tavsifi
├── .env                        # Mahfiy sozlamalar (port, DB, token)
├── run.sh                      # Ishga tushirish uchun script


# 🏠 Virtual Uyga Kirish Tizimi (Smart Home AI Access System)

AI orqali boshqariladigan zamonaviy aqlli uy kirish tizimi. Bu loyiha yuzni tanish, ovozli buyruq bilan eshikni ochish va AI agent yordamida mehmonlarni boshqarish imkonini beradi.

---

## ✨ Asosiy imkoniyatlar

- 🤖 **AI Agent (LangChain + LLaMA via Ollama):**
  - Mehmon bilan suhbat qura oladi
  - Uy egasining ovozli buyruqlarini tushunadi

- 🧠 **Yuzni tanib olish (OpenCV + Face Rec):**
  - Kiruvchilarni yuz orqali aniqlaydi
  - Tanilmagan mehmonlar loglanadi

- 🎤 **Ovoz bilan boshqaruv:**
  - Uy egasi: "Bu mening do‘stim" deb aytadi → AI unga ruxsat beradi
  - Buyruqlar: `qo‘sh`, `och`, `rad et`, va boshqalar

- 📚 **Kirish loglari (audit):**
  - Kim, qachon va qanday kirishga uringan
  - Qanday buyruq berilgan, kim ruxsat olgan

---

## 🛠 Texnologiyalar

| Texnologiya      | Maqsad                         |
|------------------|--------------------------------|
| **FastAPI**       | Backend REST API               |
| **OpenCV**        | Yuzni aniqlash (rasmlar)       |
| **LangChain**     | AI agentni yaratish            |
| **LLaMA 3 (Ollama)** | Tabiiy tilni tushunish (local LLM) |
| **SQLite/PostgreSQL** | Ma’lumotlar bazasi             |
| **Pydantic**       | Ma’lumotlar sxemasi            |
| **JWT**            | Token asosida autentifikatsiya |
| **Aiogram** *(keyinchalik)* | Telegram frontend (ixtiyoriy)   |

---

## ⚙️ Loyihani ishga tushurish

```bash
git clone https://github.com/username/smart-home-access.git
cd smart-home-access

# Muhit yaratish
python -m venv venv
source venv/bin/activate

# Kutubxonalarni o‘rnatish
pip install -r requirements.txt

# O‘rnatish uchun .env fayl yarating
cp .env.example .env

# Loyihani ishga tushurish
uvicorn app.main:app --reload
