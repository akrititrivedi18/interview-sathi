# 🎤 Interview Saathi

**AI-powered mock interview platform for Hindi, Awadhi, and Bhojpuri speaking students.**

Practice interviews, get instant AI feedback, and ace your dream job. 🚀

---

## ✨ Features

* 🎙️ Voice-based interview practice (Hinglish supported)
* 🤖 AI-generated interview questions
* 📊 Instant feedback with detailed scoring
* 📈 Grammar, structure, tone & confidence analysis
* ⭐ STAR method detection
* 🧠 Filler word detection
* ✍️ Professionally rewritten answers
* 🎮 Gamification with XP & levels

---

## 🚀 Quick Start

### 📌 Prerequisites

| Tool    | Version |
| ------- | ------- |
| Python  | 3.9+    |
| Node.js | 18+     |
| npm     | 9+      |
| ffmpeg  | any     |

### Install ffmpeg

```bash
# macOS
brew install ffmpeg

# Ubuntu/Debian
sudo apt install ffmpeg

# Windows
winget install Gyan.FFmpeg
```

---

## 📁 Project Structure

```
interview-saathi/
├── backend/
│   ├── app.py
│   ├── whisper_logic.py
│   ├── groq_logic.py
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── pages/
│   │   ├── components/
│   │   └── utils/
│   ├── index.html
│   └── package.json
├── .env.example
├── .gitignore
└── README.md
```

---

## ⚙️ Setup

### 1️⃣ Clone Repository

```bash
git clone <repo-url>
cd interview-saathi
```

Create `.env` file:

```bash
cp .env.example .env
```

Edit `.env`:

```
GROQ_API_KEY=your_groq_api_key_here
```

👉 Get API key: https://console.groq.com/

---

### 2️⃣ Backend Setup

```bash
cd backend

python -m venv venv
source venv/bin/activate      # Mac/Linux
# OR
venv\Scripts\activate         # Windows

pip install -r requirements.txt
python app.py
```

Backend runs at:
👉 http://localhost:5000

---

### 3️⃣ Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

Frontend runs at:
👉 http://localhost:5173

---

## 🎯 How to Use

1. Open http://localhost:5173
2. Click **Start Interview**
3. Choose interview type:

   * 💻 Software Engineer
   * 🤝 HR Interview
   * 🎓 MBA Interview
4. Read the AI-generated question
5. Click 🎤 and record your answer
6. Click **Analyze My Answer**
7. View detailed feedback

---

## 📊 Scoring System

```
Interview Score =
(grammar × 0.3) +
(structure × 0.3) +
(tone × 0.2) +
(confidence × 0.2)
× 10
```

Confidence formula:

```
confidence = max(0, 10 - filler_words × 1.5)
```

---

## 🏆 Gamification

| XP Range | Level              | Badge |
| -------- | ------------------ | ----- |
| 0–100    | 🌱 Beginner        | –     |
| 101–300  | 📈 Improving       | –     |
| 301+     | 🏆 Interview Ready | ⭐     |

* Each session = **50 XP**
* Score ≥ 75 → **Badge unlocked**

---

## 🔌 API Endpoints

### Health Check

```
GET /api/health
```

### Generate Question

```
POST /api/question

Request:
{ "role": "Software Engineer" }

Response:
{ "question": "Tell me about a challenging project..." }
```

### Analyze Answer

```
POST /api/analyze

Form Data:
- audio file
- role
- question
```

---

## 🛠 Tech Stack

### Backend

* Flask + Flask-CORS
* OpenAI Whisper (Speech-to-Text)
* Groq API (LLaMA 3.3 70B)
* python-dotenv

### Frontend

* React 18 + Vite
* React Router
* Tailwind CSS
* Axios
* MediaRecorder API

---

## 🚢 Deployment

### Backend

```bash
pip install gunicorn
gunicorn -w 2 -b 0.0.0.0:5000 app:app
```

### Frontend

```bash
npm run build
```

Deploy `dist/` using Nginx / Netlify / Vercel

---

## ❓ Troubleshooting

**Whisper slow download?**

```bash
python -c "import whisper; whisper.load_model('small')"
```

**Mic not working?**

* Enable browser permissions
* Use HTTPS in production

**Groq API error?**

* Check `.env` file

**ffmpeg not found?**

* Install it properly

---

## 📝 License

MIT License

---

## 💡 Vision

> *Because every student deserves a fair shot at their dream job.*

---

## 🤝 Contributing

Pull requests are welcome!
Let’s make interview prep accessible for everyone. 🌍

---

## ⭐ Support

If you like this project, give it a ⭐ on GitHub!

