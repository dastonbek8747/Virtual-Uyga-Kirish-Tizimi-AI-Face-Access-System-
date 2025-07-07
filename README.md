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
