<div align="center">

# AI-VRIS — AI Powered VR Interview Simulator

[![Status: Completed](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](#)
[![Unity](https://img.shields.io/badge/Unity-100000?style=for-the-badge&logo=unity&logoColor=white)](https://unity.com/)
[![VR](https://img.shields.io/badge/VR-Meta_Quest-045b62?style=for-the-badge)](#)
[![Python](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=green)](https://www.djangoproject.com/)
[![AI Powered](https://img.shields.io/badge/AI_Powered-Groq_&_GCP-005571?style=for-the-badge)](https://groq.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

**A Virtual Reality interview training platform powered by AI, designed to simulate realistic technical and HR interviews using speech recognition, dynamic question generation, and immersive VR interaction.**

*Uniqueness:* **AI + VR + Speech + Real-time interview simulation.**

* 🎯 **Resume-aware interviews**
* 🎤 **Voice interaction**
* 🧠 **AI-generated questions**
* 📊 **Real-time evaluation**
* 🥽 **VR-based immersive environment**

</div>

---

## 🚀 Status
✅ Major Project Completed  
✅ Demo APK Developed  
✅ Final Report Submitted  
✅ Prototype Successfully Presented  

---

## 💡 Why AI-VRIS? (Project Motivation)

Many students struggle with interview anxiety and lack access to realistic mock interview experiences. AI-VRIS was built to provide an affordable, immersive, and AI-powered platform that helps users improve confidence and communication skills before real interviews.

---

## 📸 Demo Screenshots & Video

> **Note**: Demo video and high-resolution screenshots are located in the `docs/media/` folder.

<div align="center">
  <a href="docs/media/demo_1.mp4">
    <img src="https://img.shields.io/badge/▶_Watch_Demo_Part_1-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch Demo 1" />
  </a>
  &nbsp;&nbsp;
  <a href="docs/media/demo_2.mp4">
    <img src="https://img.shields.io/badge/▶_Watch_Demo_Part_2-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch Demo 2" />
  </a>
  &nbsp;&nbsp;
  <a href="docs/media/demo_3.mp4">
    <img src="https://img.shields.io/badge/▶_Watch_Demo_Part_3-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch Demo 3" />
  </a>
</div>

### Environment & Dashboard Previews
<div align="center">
  <img src="docs/media/Main%20menu.jpg" width="45%" alt="Main Menu" />
  <img src="docs/media/Name%20and%20Role.jpg" width="45%" alt="Upload Menu" />
</div>
<br>
<div align="center">
  <img src="docs/media/Interview%20Room.png" width="30%" alt="VR Interview" />
  <img src="docs/media/Interview%20Report%20Summary.png" width="30%" alt="Candidate Summary" />
  <img src="docs/media/Report%20History.png" width="30%" alt="Reports Menu" />
</div>

---

## ⚙️ How It Works (Workflow)

1. Candidate uploads resume.
2. Resume is parsed and summarized.
3. User enters the VR environment.
4. AI interviewer asks contextual questions.
5. User responds through voice.
6. Speech is transcribed in real-time.
7. AI evaluates the response.
8. Next question is dynamically generated based on the answer.
9. Final comprehensive report is generated.

---

## 🌟 Features

### 🎤 AI Voice Interviewer
Conducts realistic spoken interviews using AI-generated speech.

### 🧠 Dynamic Question Generation
Questions adapt based on candidate responses, resume content, and the current interview stage.

### 📄 Resume Parsing
Extracts and summarizes candidate resumes to personalize the interview experience.

### 📊 AI Performance Analysis
Evaluates technical accuracy, communication quality, and behavioral confidence.

### 🥽 Immersive VR Experience
Simulates real interview pressure using an interactive VR environment.

### 🔁 Multi-Stage Interview Flow
Supports Introduction, Resume discussion, Technical rounds, HR/behavioral rounds, and a Final wrap-up.

---

## 📐 Architecture

The system follows a decoupled architecture, bridging immersive VR with heavy AI processing.

<div align="center">
  <img src="docs/media/Systems%20Architecture.jpeg" width="80%" alt="Systems Architecture" />
</div>
<br>
<div align="center">
  <img src="docs/media/Dataflow%20diagram.jpeg" width="80%" alt="Dataflow Diagram" />
</div>

```mermaid
graph TD
    %% Styling
    classDef client fill:#222,stroke:#fff,stroke-width:2px,color:#fff;
    classDef backend fill:#092E20,stroke:#fff,stroke-width:2px,color:#fff;
    classDef external fill:#005571,stroke:#fff,stroke-width:2px,color:#fff;

    A[User / VR Headset] -->|Voice Input| B[Unity VR Client]
    C[Audio Output] -->|AI Voice| A
    
    B -->|REST API Calls| D[Django REST API Backend]
    D -->|Responses & State| C
    
    D -->|Prompting| E[LLM Engine]
    D -->|Audio Processing| F[Speech-to-Text / TTS]
    D -->|Grading| G[Evaluation Engine]
    D -->|Aggregating| H[Report Generation]
    
    class B client;
    class D backend;
    class E,F external;
```

---

## 🛠️ Tech Stack

### Frontend / VR
* Unity 3D
* XR Interaction Toolkit
* C#

### Backend
* Python
* Django
* Django REST Framework

### AI & Speech
* Groq API (Fast LLM Inference)
* Google Generative AI
* Google Cloud Speech-to-Text
* PlayAI TTS

### Database
* SQLite (Dev)
* PostgreSQL Ready (Prod)

### Deployment
* Gunicorn
* WhiteNoise
* Render / Heroku Compatible

---

## 📈 Resume-Grade Metrics

* **Integrated 4+ AI services** seamlessly into a single VR application.
* **Supported multi-stage interview workflows** adapting to 5 distinct conversational phases.
* **Processed speech responses in near real-time**, ensuring fluid VR interaction.
* **Built scalable REST APIs** supporting dynamic session management and robust state handling.
* **Reduced interview generation latency** significantly using fast-inference engines like Groq.

---

## 🧩 API Documentation

Core REST endpoints driving the VR experience:

| Endpoint             | Method | Description                  |
| -------------------- | ------ | ---------------------------- |
| `/api/interview/step/` | POST   | Generate next interview step |
| `/api/audio-to-text/`  | POST   | Convert speech to text       |
| `/api/resume/upload/`  | POST   | Upload and parse resume      |
| `/api/reports/`        | GET    | Fetch interview reports      |

---

## 📂 Folder Structure

```text
ai-vris/
├── VR-Game-Jam-Template-main/   -> Unity VR frontend client
├── vr_backend/                  -> Django backend API server
│   ├── interviewer/services/    -> AI orchestration (LLM, STT, TTS)
│   ├── manage.py                -> Django CLI
│   └── requirements.txt         -> Python dependencies
└── docs/media/                  -> Assets for documentation
```

---

## ⚠️ Challenges Faced

* **Synchronizing VR interaction** with backend AI responses to maintain immersion.
* **Managing speech recognition latency** across network requests.
* **Designing dynamic interview flow logic** that adapts gracefully to unpredictable human speech.
* **Handling real-time audio processing** securely between Unity and Django.
* **Integrating multiple AI services** (GCP, Groq, PlayAI) into a cohesive pipeline.

---

## 🔮 Future Improvements

* Multiplayer interview panels (e.g., multiple AI recruiters).
* Facial expression analysis & Eye contact tracking.
* Emotion recognition from vocal tone.
* Offline AI inference for completely untethered setups.
* Multi-language interview support.
* Cloud analytics dashboard for long-term tracking.
* Recruiter-side evaluation portal.

---

## 🚀 Installation & Setup Guide

### 1. Backend Setup

```bash
# Clone the repository
git clone https://github.com/Maxy747/ai-vris
cd ai-vris/vr_backend

# Set up Python virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Environment Variables: Create a `.env` file with your keys
# GROQ_API_KEY=...
# GOOGLE_APPLICATION_CREDENTIALS=/path/to/gcp.json

# Run Server
python manage.py migrate
python manage.py runserver 0.0.0.0:8000
```

### 2. Unity Setup

1. Open **Unity Hub**.
2. Open the `VR-Game-Jam-Template-main` folder.
3. Install required XR packages via the Unity Package Manager.
4. Load the **Interview scene** from `Assets/Scenes`.
5. Point the API base URL to `http://localhost:8000`.
6. Press Play!

---

## ☁️ Deployment

* Backend configured for cloud deployment.
* Supports **Gunicorn + WhiteNoise** for static asset delivery.
* **Render/Heroku compatible** via included `Procfile` and `build.sh`.

---

## 👥 Team

* **Mazin Abdul Azeez** — AI & Backend Development
* **Libin** — VR Development
* **Ahmad** — System Integration
* **Marwan** — Additional Contributions

---

## 📄 License
This project is licensed under the MIT License.
