MandarinGo - AI-Powered Chinese Mandarin Learning Platform
=========================================================

An adaptive Chinese learning platform that uses AI to give real-time, personalized feedback on pronunciation, writing, speaking, and HSK exam preparation.

Website: https://learningmandarin.cn


Why MandarinGo?
----------------

Learning Chinese Mandarin is challenging. The tones are confusing, the characters look like puzzles, and most existing apps give you flashcards but no real feedback on your pronunciation or writing.

MandarinGo fills this gap with AI-powered features that simulate having a personal Chinese tutor available 24/7.


Comparison with Other Tools
----------------------------

Feature                    | Duolingo | HelloChinese | Pleco | MandarinGo
---------------------------|----------|--------------|-------|-----------
AI Pronunciation Scoring   | No       | Basic        | No    | Yes (real-time)
Character Writing Practice | No       | No           | No    | Yes (stroke order + canvas)
HSK Mock Exam (1-6 + 3.0)  | No       | No           | No    | Yes (full mock + analysis)
AI Speaking Tutor          | No       | Limited      | No    | Yes (6 scenarios)
Adaptive Learning Path     | Basic    | No           | No    | Yes (placement-based)
Vocabulary SRS             | Basic    | Basic        | No    | Yes (12,000+ words)
Listening Training         | No       | No           | No    | Yes (retell method)
Dictionary                 | No       | No           | Yes   | Yes (tap-to-select)


Core Features
--------------

1. AI Pronunciation Assessment
   Record yourself reading Chinese sentences. Our AI model (Qwen2.5-1.5B quantized) analyzes your pronunciation in real-time, scoring:
   - Tone accuracy (ma flat vs ma dipping)
   - Initial consonants (zh/ch/sh vs z/c/s distinction)
   - Final vowels (-an vs -ang distinction)
   You get an overall score plus detailed breakdown for each component.

2. Speaking Practice with AI Tutor
   Practice Chinese conversation across 6 real-life scenarios:
   - Daily Life
   - Food and Dining
   - Travel
   - Shopping
   - Work and Office
   - Culture and Traditions
   The AI tutor responds naturally in Chinese, corrects mistakes, and suggests better expressions. Supports voice input via Whisper AI transcription.

3. Chinese Character Writing
   Learn to write 10,000+ Chinese characters with:
   - Stroke order animation
   - Interactive writing canvas (mouse or touchscreen)
   - AI match scoring comparing your writing to correct form

4. HSK Mock Exam
   Full mock exams for all HSK levels:
   - HSK 1-6 (classic six-level system)
   - HSK 3.0 (new nine-level system with i+1 content push)
   - Instant score breakdown by section
   - Wrong question collection for targeted review

5. Vocabulary Learning with Spaced Repetition
   12,000+ word bank organized by HSK levels:
   - Learn mode: New words with example sentences and audio
   - Practice mode: Multiple choice and fill-in-the-blank
   - Review mode: SRS scheduling based on forgetting curve

6. Listening Training
   Listen to Chinese audio at your level, then retell what you understood in English. AI evaluates comprehension and identifies gaps.

7. Dictionary with Tap-to-Select
   Read any Chinese text and tap words for instant definitions, pinyin, and example sentences.

8. Smart Study Plan
   Auto-generated daily and weekly plans based on:
   - Current HSK level
   - Mastered vs struggling words
   - Available study time
   - Streak-based check-in rewards (30/100/365 days)


Two Learning Modes
-------------------

Classic Mode
   Focused on HSK preparation and systematic proficiency improvement. Clean, modern interface for efficient study.

Archaeology Mode
   Immersive archaeological narrative where you excavate ancient Chinese character artifacts. Complete lessons to collect Hanzi treasures in a museum-style gallery. Gamified experience beyond traditional test prep.

Both modes cover identical learning content. Switch anytime.


Technology Stack
-----------------

Frontend: Vue 3 + Element Plus + Vite
Backend: FastAPI (Python) + SQLite
AI Models: Qwen2.5-1.5B (quantized) for pronunciation assessment, Whisper for speech transcription
Reverse Proxy: Caddy
Server: uvicorn (ASGI)
Deployment: Self-hosted on single cloud server

The entire system runs on a single server with quantized AI models. No expensive API calls. No cloud ML dependencies.


Target Audience
----------------

- Beginners starting from HSK 1 (no prior Chinese needed)
- Intermediate learners preparing for HSK 3-4
- Advanced learners targeting HSK 5-6
- Self-study learners wanting AI feedback without a tutor
- University students supplementing Chinese courses
- Expats in China needing practical speaking skills


Project Structure
-----------------

mandaringo/
  frontend/          Vue 3 + Vite application
    src/
      views/         Page components (Home, Pronunciation, Practice, etc.)
      components/    Shared components (Header, Sidebar, RewardModal, etc.)
      stores/        Pinia state management (mode, collection, auth, etc.)
      data/          Static data (hanziTreasure, etc.)
      api/           API client modules
    public/          Static assets and landing pages
  backend/           FastAPI Python backend
    app/
      main.py        Application entry, routing, SPA fallback
      routers/       API route modules (admin, hsk, etc.)
    data/            HSK exam banks, vocabulary data
  docs/              Documentation


Getting Started
----------------

Prerequisites:
- Node.js 18+
- Python 3.10+
- npm or yarn

Frontend:
  cd frontend
  npm install
  npm run build

Backend:
  cd backend
  pip install -r requirements.txt
  uvicorn app.main:app --host 0.0.0.0 --port 8004

The frontend builds to frontend/dist/ which is served by the backend as static files.


License
--------

Proprietary. All rights reserved.


Links
------

Website: https://learningmandarin.cn
HSK Preparation: https://learningmandarin.cn/hsk-prep.html
Pronunciation Guide: https://learningmandarin.cn/pronunciation-guide.html
Speaking Practice: https://learningmandarin.cn/speaking-practice.html
Chinese Writing: https://learningmandarin.cn/chinese-writing.html
Vocabulary Learning: https://learningmandarin.cn/vocabulary-learning.html
Complete Guide: https://learningmandarin.cn/learn-chinese-online.html
