# 📚 Faga Adaptive English Teacher

An AI-powered personalized English reading application that helps advanced learners improve their skills through adaptive content recommendation and deep LLM analysis.



## ✨ Key Features

- **🧠 Smart Recommendation System**: Suggests articles based on your CEFR level calculation and interest profile.
- **📝 Dual-Mode Reader**:
    - **Clean Mode**: A distraction-free, beautifully typographed reading environment.
    - **Learning Mode**: One-click toggles deep analysis, highlighting key vocabulary, collocations, and sentence structures.
- **🤖 Deep AI Analysis**: Powered by **Gemini 2.5 Flash**, the system extracts:
    - **Vocabulary**: CEFR-target words with definitions.
    - **Collocations**: Native-like phrases and idioms.
    - **Sentence Patterns**: Advanced grammatical structures and rhetorical devices.
- **🌍 Multi-Source Import**: Automatically aggregates content from Wikipedia, VOA Learning English, and NewsAPI.
- **📊 Progress Tracking**: Tracks reading history, vocabulary bank, and learning statistics.

## 🛠️ Tech Stack

### Frontend
- **Framework**: React 18 + TypeScript + Vite
- **Styling**: TailwindCSS (v4) + Typography Plugin
- **Markdown**: React Markdown for perfect rendering
- **Icons**: Lucide React

### Backend
- **Server**: Flask (Python)
- **Database**: SQLite + SQLAlchemy
- **AI/LLM**: Google Gemini API (gemini-2.5-flash)
- **Vectors**: FAISS + Sentence Transformers (for recommendation)
- **Pipeline**: Pydantic for structured data validation

## 🚀 Quick Start

### 1. Required Dependencies

**System-level dependencies**
- **Python**: 3.10+
- **Node.js**: 18+
- **FFmpeg**: Required for audio/voice features (English Pilot STT/TTS workflows)
- **Git**: For cloning the repository

**Python dependencies**
- Install from `requirements.txt` (primary runtime dependency file).

**Frontend dependencies**
- Installed via `npm install` in `frontend/`.

### 🔐 API Keys & Configuration

Create a `.env` file at the project root:
```
GEMINI_API_KEY=your_gemini_key
NEWS_API_KEY=your_newsapi_key
HF_TOKEN=your_huggingface_token
SECRET_KEY=change-me
```

**Required keys**
- `GEMINI_API_KEY`: Enables article analysis and translation features.
- `NEWS_API_KEY`: Enables NewsAPI ingestion.
- `HF_TOKEN`: Enables Hugging Face models (Qwen proficiency + image generation).

### 🐍 Python Virtual Environment Setup

#### Option A: Using `venv`
```bash
python -m venv .venv
# Windows
.venv\\Scripts\\activate
pip install --upgrade pip
pip install -r requirements.txt
```

> Note: even if you use `uv` to create/activate a virtual environment, install runtime dependencies from `requirements.txt`.

### 2. Run Application

Start both Backend and Frontend with a single command:

- On **Windows**, use `run_all.bat` instead.
- **Backend API**: http://localhost:5000
- **Frontend App**: http://localhost:5173

- or
 ```bash
./start_all.sh
```

## 🧩 Comprehensive Installation Guide

This section covers a clean install from scratch, including system dependencies, Python/Node setup, API keys, and OS-specific steps.

### ✅ Verification Checklist
After starting, verify:
- Backend running at `http://localhost:5000`
- Frontend running at `http://localhost:5173`
- `.env` contains your API keys

## 📖 User Guide

Please check our landing page:

https://lqc-wr.github.io/Adaptive-English-Teacher-User-Guide/#how

## 📂 Project Structure

```
faga-adaptive-english-teacher/
├── backend/
│   ├── app.py                   # Flask API Entry
│   ├── models.py                # Database Schema
│   ├── recommender.py           # Recommendation Engine
│   └── data_pipeline/           # ETL & AI Analysis
│       ├── llm_analyzer.py      # Gemini Interface
│       └── pipeline.py          # Main Pipeline Script
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   └── Reader.tsx       # Core Reading Component
│   │   ├── services/            # API Client
│   │   └── App.tsx              # Main Router & Logic
│   └── package.json             # Frontend Dependencies
├── scripts/
│   ├── create_test_user.py      # User Helper
│   └── reanalyze_article.py     # Debug Helper
└── start_all.sh                 # Startup Script
```

## 📝 Latest Updates

### v1.0.0 Refactor
- **Frontend Rewrite**: Moved from Vanilla JS to React/TypeScript for better state management.
- **Design System**: Adopted TailwindCSS for a modern, responsive UI.
- **LLM Upgrade**: Upgraded to `gemini-2.5-flash` with dynamic context window handling (6k tokens) and full-text analysis capabilities.
- **Pipeline Robustness**: Enhanced error handling and dynamic retry logic for data fetching.
