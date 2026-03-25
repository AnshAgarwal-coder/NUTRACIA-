# 🌿 Nutracía — AI-Powered Wellness Platform

"Imagine a world where your wellness routine isn't scattered across apps, tabs, or to-do lists, but unified, intuitive, and designed just for you. That is the vision behind Nutracia."

📖 About The Project
Nutracia is an intelligent, all-in-one AI-powered wellness and health platform built to guide users day-by-day toward total well-being. Whether you are planning a workout, refining your skincare, adjusting your diet, or managing a health condition, Nutracia combines Artificial Intelligence with beautifully crafted design to empower you with knowledge and actionable routines.

We believe wellness should feel personal, not prescriptive. With Nutracia, your journey to feeling better isn't just easier—it's smarter, calmer, and truly yours.

✨ Key Features
🧠 HealNav: AI Medical Assistant & Symptom Checker
AI Symptom Checker: Input your symptoms (e.g., fever, cough, fatigue) and receive personalized health insights, urgency levels, and possible conditions.

Medical Bot: An intelligent chat interface that provides instant health guidance, workout advice, nutrition tips, and stress management techniques.

Health Education Center: A curated library covering Heart Health, Mental Wellness, Sleep Health, and Preventive Care.

🏋️ Personalized Workout Plans
[cite_start]Dynamic Routines: Tailored fitness plans ranging from Beginner to Advanced, including HIIT Cardio, Core Strength, Mobility Flows, and Upper Body Strength[cite: 56, 62].
[cite_start]Guided Tutorials: Step-by-step video integrations and instructions targeting specific muscle groups and flexibility goals[cite: 65, 66].

🥗 Intelligent Diet & Nutrition
[cite_start]Custom Meal Plans: Access specialized diets such as the Mediterranean Diet, Keto, DASH, and Plant-Based Nutrition[cite: 81, 84].
[cite_start]Allergy & Preference Aware: AI curates food recommendations based on your vital stats, dietary preferences (e.g., Vegetarian), and allergies (e.g., Dairy, Gluten)[cite: 40, 41, 49].

✨ Science-Backed Skincare
[cite_start]Custom Routines: Anti-aging protocols, hydration boosts, and acne defense routines tailored specifically to your skin type (e.g., Oily, Dry, Combination)[cite: 74].

Mental & Emotional AI
🎙️ Voice Therapy (Real-Time AI): A flagship AI therapist providing empathetic voice responses with ultra-low latency (<800ms), powered by Deepgram Nova-2 and LLaMA-3.

📖 Anne's Diary (Multimodal AI): An emotional journal where users can upload photos or voice notes for Gemini 1.5 Flash to analyze and provide deep contextual insights.

😊 Smile Detection (Emotional Gate): A privacy-first awareness gate using face-api.js that detects your mood via webcam before login to prompt personalized wellness check-ins.

🧘 Mind & Soul (CBT Tools): A suite of mental resilience tools including 4-7-8 breathing, guided meditations, sleep protocols, and cognitive restructuring exercises.

🏥 Care & Connectivity
📍 Nearby Care (Live Google Maps): Instantly locate psychiatrists, therapists, and clinics within 5km, including ratings, hours, and direct booking options.

🤖 AI Health Chatbot: A 24/7 floating assistant trained on medical data to answer queries about any module or provide immediate wellness advice.

🛒 AI-Powered Smart Shopping

Budget-Aware Recommendations: Tell the AI what you need (e.g., "I need high protein supplements for my workout under ₹1000").
Curated Cart: The AI analyzes products, checks active ingredients, compares prices across platforms, and builds a smart cart for you in seconds.
---

## ⚡ Quick Start (3 steps)

```bash
# 1. Install all dependencies
npm run install:all

# 2. Set up environment variables
cp server/.env.example server/.env
# Edit server/.env and fill in your API keys

# 3. Run both client + server
npm run dev
```

Open `http://localhost:5173` in your browser.

---

## 🔑 Required API Keys

All services have **free tiers** — no paid subscriptions needed.

| Service | Where to get | Used for |
|---------|-------------|---------|
| `MONGO_URI` | [cloud.mongodb.com](https://cloud.mongodb.com) (free M0) | Database |
| `GROQ_API_KEY` | [console.groq.com](https://console.groq.com) (free, no card) | AI Chat (primary LLM) |
| `GEMINI_API_KEY` | [aistudio.google.com](https://aistudio.google.com/app/apikey) (free, no card) | Grocery AI + Diary analysis |
| `OPENAI_API_KEY` | [platform.openai.com](https://platform.openai.com) ($5 free credit) | AI fallback |
| `DEEPGRAM_API_KEY` | [console.deepgram.com](https://console.deepgram.com) ($200 free credit) | Voice STT + TTS |
| `CLOUDINARY_*` | [cloudinary.com](https://cloudinary.com) (free 25GB) | Diary media uploads |
| `GOOGLE_MAPS_API_KEY` | [console.cloud.google.com](https://console.cloud.google.com) ($200/mo free) | Nearby care map |
| `JWT_SECRET` | Generate: `openssl rand -hex 64` | Auth tokens |

> **Minimal setup:** Only `MONGO_URI`, `GROQ_API_KEY`, and `JWT_SECRET` are required to run core features. Everything else enhances optional features.

---

## 📁 Project Structure

```
nutracia/
├── package.json          ← root (runs both with concurrently)
├── client/               ← React + Vite frontend
│   ├── src/
│   │   ├── App.jsx
│   │   ├── pages/        ← HomePage, WorkoutPage, DiaryPage, etc.
│   │   ├── components/   ← Header, Modal, CircularGallery, AIChatbot...
│   │   └── utils/api.js
│   └── vite.config.js    ← proxies /api → localhost:5000
└── server/               ← Node.js + Express backend
    ├── .env.example      ← copy to .env and fill keys
    └── src/
        ├── index.js      ← entry point
        ├── routes/       ← auth, chat, diary, grocery, voice, wellness, maps
        ├── models/       ← User, DiaryEntry, ChatHistory
        └── services/     ← groq, gemini, deepgram, cloudinary
```

---

## 🌟 Features

| Feature | Route | Description |
|---------|-------|-------------|
| 🏋️ Workout Plans | `/workout` | 8 plans in circular WebGL gallery + YouTube embeds |
| ✨ Skincare Routines | `/skincare` | 8 science-backed routines with step-by-step guide |
| 🥗 Diet Plans | `/diet` | 8 nutrition plans (Keto, Mediterranean, Plant-based...) |
| 🧠 Mind & Soul | `/mind-soul` | Meditation library, 4-7-8 breathing, timer, mood tracker |
| 🩺 Health Platform | `/health` | Symptom checker, medical chatbot, health education |
| 🛒 AI Grocery | `/order-up` | Gemini-powered smart shopping with budget filtering |
| 📔 Anne's Diary | `/diary` | Emotional journal with image/audio/video + AI mood analysis |
| 🎙️ Voice Therapy | `/voice` | Animated orb, voice input (Web Speech API), AI therapist Anne |
| 🗺️ Nearby Care | `/nearby` | Google Maps to find doctors/therapists within 5km |
| 🤖 AI Chatbot | (floating) | 24/7 health coach powered by Groq LLaMA-3 |

---

## 🛠️ Tech Stack

- **Frontend:** React 18 + Vite + Tailwind CSS + Framer Motion
- **Backend:** Node.js + Express (ESM)
- **Database:** MongoDB Atlas (Mongoose)
- **AI:** Groq LLaMA-3 (primary) + OpenAI GPT-3.5 (fallback) + Gemini 1.5 Flash
- **Voice:** Deepgram Nova-2 STT + Aura TTS + Web Speech API
- **Media:** Cloudinary (diary uploads)
- **Maps:** Google Maps Places API

---

## 📝 Notes

- The Vite dev server proxies all `/api` requests to `http://localhost:5000` — no CORS issues in dev
- Voice therapy uses browser's Web Speech API for STT (free, no API needed), with Deepgram as optional backend TTS
- Diary uploads require Cloudinary to be configured; text-only entries work without it
- Maps feature requires Google Maps API key; shows demo results without it
- The circular gallery is a CSS scroll-based carousel that works on all browsers
