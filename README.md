# 🌾 AgriSense AI — Multi-Agent Smart Agriculture Platform

<div align="center">

![AgriSense AI Banner](https://img.shields.io/badge/AgriSense-AI-green?style=for-the-badge&logo=leaf)
![Python](https://img.shields.io/badge/Python-3.11+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.109+-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![React](https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react&logoColor=black)
![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.4+-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![Gemini](https://img.shields.io/badge/Google%20Gemini-1.5%20Flash-4285F4?style=for-the-badge&logo=google&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

**An intelligent multi-agent system where 6 specialized AI agents collaborate to deliver real-time smart farming decisions — powered by Google Gemini.**

[Features](#-features) • [Architecture](#-architecture) • [Tech Stack](#-tech-stack) • [Setup](#-installation--setup) • [API Docs](#-api-endpoints) • [Screenshots](#-screenshots)

</div>

---

## 📖 Overview

**AgriSense AI** is a multi-agent smart agriculture platform that revolutionizes modern farming by deploying **6 specialized AI agents** — Weather, Soil, Crop, Irrigation, Pest, and Harvest — that collaborate through a central orchestrator to provide farmers with accurate, real-time, and actionable insights.

Unlike traditional single-model AI systems, AgriSense AI uses **inter-agent communication** where each agent contributes domain-specific expertise, and their combined intelligence produces context-aware recommendations — just like a team of expert agronomists sitting in one room.

The platform is powered by **Google Gemini 1.5 Flash** for natural-language reasoning, a **FastAPI** backend for high-performance APIs, and a stunning **React + TailwindCSS** dashboard for the frontend.

---

## 🎯 Problem Statement

Modern farmers face persistent challenges:

- ❌ **Unpredictable weather** affecting irrigation and harvesting schedules
- ❌ **Late pest detection** leading to significant crop loss
- ❌ **Over/under-fertilization** reducing yield and soil health
- ❌ **Poor soil monitoring** without actionable insights
- ❌ **Mistimed harvesting** causing quality degradation
- ❌ **Fragmented data** from isolated tools with no unified advisory

**Traditional systems provide isolated data points. AgriSense AI solves this by making multiple AI agents collaborate** — combining weather, soil, crop, and pest intelligence into one unified recommendation.

---

## ✨ Features

### 🤖 Multi-Agent Intelligence
- **6 specialized AI agents** working in coordination
- **Central orchestrator** that manages inter-agent communication
- **Structured JSON outputs** from each agent
- **Context-aware recommendations** based on real farm data
- **Agent reasoning logs** for transparency and debugging

### 🎨 Modern Frontend (React + TailwindCSS)
- Beautiful, responsive dashboard with real-time agent status
- Interactive charts (Recharts) for weather, soil, and crop trends
- Live agent chat interface with **thought-bubble visualization**
- Farm and crop management with full CRUD operations
- Dark/Light theme toggle
- Smooth animations with Framer Motion
- Mobile-first responsive design

### ⚙️ Robust Backend (FastAPI + Python)
- Async-first RESTful API with auto-generated Swagger docs (`/docs`)
- SQLAlchemy ORM with Alembic migrations
- JWT-based authentication and authorization
- Rate limiting and CORS middleware
- Structured logging with error tracking
- Clean layered architecture: routes → services → agents → database
- Pydantic-based request/response validation

### 🧠 AI Layer (Google Gemini 1.5 Flash)
- Domain-specific system prompts for each agent
- Structured JSON output parsing with fallback handling
- Context memory per conversation
- Free-tier friendly (runs smoothly on CPU-based machines)
- Retry logic and error recovery

### 🗄️ Database (SQLite → PostgreSQL Ready)
- 10+ normalized tables with proper relationships
- Historical weather, soil, and pest data tracking
- Agent conversation logs for full audit trail
- Easy migration to PostgreSQL for production

---

## 🏗️ Architecture

### Multi-Agent Orchestration Flow

```
                    ┌──────────────────────┐
                    │   User Query / Farm  │
                    │       Context        │
                    └──────────┬───────────┘
                               │
                    ┌──────────▼───────────┐
                    │   ORCHESTRATOR       │
                    │  (Central Brain)     │
                    └──────────┬───────────┘
                               │
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
   ┌────▼────┐          ┌─────▼─────┐         ┌──────▼──────┐
   │ Weather │◄────────►│   Soil    │◄───────►│    Crop     │
   │  Agent  │          │   Agent   │         │    Agent    │
   └────┬────┘          └─────┬─────┘         └──────┬──────┘
        │                     │                      │
        └──────────────────────┼──────────────────────┘
                               │
                    ┌──────────▼───────────┐
                    │  Combined Insights   │
                    └──────────┬───────────┘
                               │
        ┌──────────────────────┼──────────────────────┐
        │                      │                      │
   ┌────▼────┐          ┌─────▼─────┐         ┌──────▼──────┐
   │Irrigation│         │   Pest    │         │  Harvest    │
   │  Agent  │          │   Agent   │         │   Agent     │
   └─────────┘          └───────────┘         └─────────────┘
                               │
                    ┌──────────▼───────────┐
                    │  Final Smart Advice  │
                    │      to Farmer       │
                    └──────────────────────┘
```

### Agent Responsibilities

| Agent | Role | Key Functions |
|-------|------|---------------|
| 🌤️ **Weather Agent** | Forecast Analyst | Fetches weather data, predicts rain, temperature, humidity, wind |
| 🌱 **Soil Agent** | Soil Health Expert | Monitors NPK, pH, moisture, recommends soil treatment |
| 🌾 **Crop Agent** | Crop Growth Monitor | Tracks crop stage, health, growth rate, yield prediction |
| 💧 **Irrigation Agent** | Water Management | Decides when & how much to irrigate based on soil + weather |
| 🐛 **Pest Agent** | Pest Detection | Identifies pests, suggests organic/chemical remedies |
| 🚜 **Harvest Agent** | Harvest Planner | Predicts optimal harvest time, yield estimation |
| 🌿 **Fertilizer Agent** | Nutrient Advisor | Schedules fertilizer application based on crop stage |

---

## 🛠️ Tech Stack

| Layer | Technologies |
|-------|--------------|
| **Frontend** | React 18, Vite, TailwindCSS, Recharts, Framer Motion, Axios, React Router v6, Lucide React |
| **Backend** | Python 3.11+, FastAPI, SQLAlchemy, Pydantic, Alembic, Uvicorn |
| **AI/LLM** | Google Gemini 1.5 Flash API |
| **Database** | SQLite (development) / PostgreSQL (production-ready) |
| **Authentication** | JWT (python-jose, passlib, bcrypt) |
| **DevOps** | Docker, Docker Compose, GitHub Actions |
| **Testing** | Pytest (backend), Vitest (frontend) |
| **Code Quality** | Black, Ruff, ESLint, Prettier |

---

## 📁 Project Structure

```
agri-multiagent-platform/
│
├── backend/                    # FastAPI + Gemini agents
│   ├── app/
│   │   ├── agents/             # 6 AI agents + orchestrator
│   │   ├── api/                # API routes
│   │   ├── core/               # Config, database, security
│   │   ├── crud/               # Database operations
│   │   ├── models/             # SQLAlchemy models
│   │   ├── schemas/            # Pydantic schemas
│   │   ├── services/           # Business logic
│   │   └── utils/              # Helpers
│   ├── database/               # DB init & seed
│   ├── tests/                  # Pytest tests
│   ├── requirements.txt
│   └── main.py
│
├── frontend/                   # React + TailwindCSS
│   ├── src/
│   │   ├── components/         # Reusable UI components
│   │   ├── pages/              # Page components
│   │   ├── services/           # API calls
│   │   ├── hooks/              # Custom hooks
│   │   ├── context/            # React context
│   │   └── styles/             # Global styles
│   ├── public/
│   ├── package.json
│   └── vite.config.js
│
├── database/                   # SQL schemas & migrations
│   ├── schema.sql
│   ├── seed.sql
│   └── migrations/
│
├── docs/                       # Documentation
│   ├── ARCHITECTURE.md
│   ├── API_DOCUMENTATION.md
│   └── screenshots/
│
├── scripts/                    # Automation scripts
│   ├── setup.sh
│   └── start_backend.sh
│
├── .gitignore
├── .env.example
├── LICENSE
└── README.md
```

---

## 🚀 Installation & Setup

### Prerequisites

Before you begin, ensure you have:

- ✅ **Python 3.11+** — [Download](https://www.python.org/downloads/)
- ✅ **Node.js 20+** — [Download](https://nodejs.org/)
- ✅ **Git** — [Download](https://git-scm.com/)
- ✅ **Google Gemini API Key** — [Get Free Key](https://aistudio.google.com/apikey)

### Step 1: Clone the Repository

```bash
git clone https://github.com/vishakha2121/agri-multiagent-platform.git
cd agri-multiagent-platform
```

### Step 2: Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

# Setup environment variables
cp .env.example .env
# Now edit .env and add your GEMINI_API_KEY

# Initialize database
python database/init_db.py

# Seed sample data
python database/seed_data.py

# Run the backend server
uvicorn main:app --reload --port 8000
```

Backend will be available at: **`http://localhost:8000`**
API Documentation: **`http://localhost:8000/docs`**

### Step 3: Frontend Setup

Open a **new terminal**:

```bash
cd frontend

# Install dependencies
npm install

# Setup environment variables
cp .env.example .env

# Run development server
npm run dev
```

Frontend will be available at: **`http://localhost:5173`**

### Step 4: Environment Variables

**Backend `.env` file:**

```env
# Gemini API
GEMINI_API_KEY=your_gemini_api_key_here
GEMINI_MODEL=gemini-1.5-flash

# Database
DATABASE_URL=sqlite:///./database/agrisense.db

# JWT
SECRET_KEY=your_super_secret_key_change_this
ALGORITHM=HS256
ACCESS_TOKEN_EXPIRE_MINUTES=30

# CORS
ALLOWED_ORIGINS=http://localhost:5173,http://localhost:3000

# App
APP_NAME=AgriSense AI
DEBUG=True
```

**Frontend `.env` file:**

```env
VITE_API_BASE_URL=http://localhost:8000/api/v1
VITE_APP_NAME=AgriSense AI
```

---

## 🔌 API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| **Auth** | | |
| POST | `/api/v1/auth/register` | Register new user |
| POST | `/api/v1/auth/login` | Login and get JWT token |
| GET | `/api/v1/auth/me` | Get current user info |
| **Agents** | | |
| POST | `/api/v1/agents/orchestrate` | Multi-agent orchestration query |
| GET | `/api/v1/agents/weather` | Weather agent insights |
| GET | `/api/v1/agents/soil` | Soil agent insights |
| GET | `/api/v1/agents/crop` | Crop agent insights |
| GET | `/api/v1/agents/irrigation` | Irrigation recommendations |
| GET | `/api/v1/agents/pest` | Pest detection results |
| GET | `/api/v1/agents/harvest` | Harvest planning |
| **Farms** | | |
| GET | `/api/v1/farms` | List all farms |
| POST | `/api/v1/farms` | Create new farm |
| GET | `/api/v1/farms/{id}` | Get farm details |
| PUT | `/api/v1/farms/{id}` | Update farm |
| DELETE | `/api/v1/farms/{id}` | Delete farm |
| **Crops** | | |
| GET | `/api/v1/crops` | List crops |
| POST | `/api/v1/crops` | Create crop |
| **Dashboard** | | |
| GET | `/api/v1/dashboard/stats` | Dashboard statistics |

**Full interactive API docs:** `http://localhost:8000/docs`

---

## 📸 Screenshots

### 🏠 Dashboard
![Dashboard](docs/screenshots/dashboard.png)

### 🤖 Agents Overview
![Agents](docs/screenshots/agents-page.png)

### 🌤️ Weather Agent
![Weather Agent](docs/screenshots/weather-agent.png)

### 💬 Agent Chat Interface
![Agent Chat](docs/screenshots/agent-chat.png)

> 📌 *Add your own screenshots after running the project. Create a `docs/screenshots/` folder and place images there.*

---

## 🎓 Learning Outcomes

This project demonstrates hands-on experience with:

- ✅ **Multi-agent AI system design** and orchestration
- ✅ **LLM prompt engineering** with Google Gemini
- ✅ **Clean architecture** in FastAPI (routes → services → agents)
- ✅ **Modern React** with hooks, context, and custom hooks
- ✅ **Full-stack integration** (frontend ↔ backend ↔ AI ↔ DB)
- ✅ **Database design** with SQLAlchemy ORM and migrations
- ✅ **RESTful API** best practices and JWT authentication
- ✅ **Responsive UI design** with TailwindCSS
- ✅ **Chart visualization** with Recharts
- ✅ **Production-ready patterns** (logging, error handling, testing)

---

## 🗺️ Roadmap

- [x] **Phase 1:** Backend setup + 6 agents + Gemini integration
- [x] **Phase 2:** Database schema + seed data
- [x] **Phase 3:** React dashboard + agent pages
- [x] **Phase 4:** Charts, animations, theme toggle
- [ ] **Phase 5:** Voice input for farmers (Hindi + English)
- [ ] **Phase 6:** Mobile app (React Native)
- [ ] **Phase 7:** IoT sensor integration (real-time data)
- [ ] **Phase 8:** Satellite imagery for crop health
- [ ] **Phase 9:** Multi-language support (Hindi, Marathi, Tamil)
- [ ] **Phase 10:** Offline mode for rural areas

---

## 🧪 Running Tests

### Backend Tests
```bash
cd backend
pytest -v
```

### Frontend Tests
```bash
cd frontend
npm run test
```

---

## 🐳 Docker Deployment

```bash
# Build and run all services
docker-compose up --build

# Backend: http://localhost:8000
# Frontend: http://localhost:5173
```

---

## 🤝 Contributing

This is a practice and portfolio project. Contributions, issues, and feature requests are welcome!

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👩‍💻 Author

**Vishakha**
- 🐙 GitHub: [@vishakha2121](https://github.com/vishakha2121)
- 💼 LinkedIn: [Your LinkedIn Profile](https://linkedin.com/in/yourprofile)
- 📧 Email: your.email@example.com

---

## 🙏 Acknowledgments

- 🌾 **Google Gemini API** for powering the AI agents
- ⚡ **FastAPI** community for the amazing framework
- ⚛️ **React** and **TailwindCSS** communities
- 🌱 Open-source agriculture datasets and research papers

---

## ⭐ Show Your Support

If you found this project helpful or interesting, please give it a ⭐ on GitHub!

---

<div align="center">

**Made with 💚 for farmers and AI enthusiasts**

🌾 **AgriSense AI** — *Smart Farming, Smarter Decisions* 🌾

</div>