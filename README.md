# AI Exam & Proctoring Platform

An interview-focused, demo-scale online exam system with AI-assisted proctoring.

This project demonstrates **clean system design**, **explainable AI**, and **real-time monitoring** — without over-engineering.

---

## 🎯 Problem Statement

Online exams suffer from cheating due to lack of effective monitoring.
Most solutions rely on:
- continuous video streaming
- heavy deep learning
- high infrastructure cost
- black-box decisions

This project solves the problem using **event-driven + snapshot-based proctoring**.

---

## 🧠 Key Design Decisions

### Why snapshots instead of video?
- Lower bandwidth & cost
- Better privacy
- Easier explainability

### Why rule-based AI?
- Transparent decisions
- Easy to justify in interviews
- Sufficient for demo-scale systems

### Why WebSockets?
- Real-time warnings
- No polling
- Event-based communication

---

## 👥 User Roles

| Role | Capabilities |
|----|----|
| Student | Take exam, monitored in real time |
| Proctor | Create exams, review suspicious activity |
| Admin (optional) | Manage users and roles |

Single application with **RBAC**, not multiple apps.

---

## 🧱 Architecture Overview

Browser (React)
→ FastAPI backend
→ AI inference (OpenCV + MediaPipe)
→ PostgreSQL
→ WebSockets for live warnings

No Kafka.  
No video streaming.  
No deep learning models.

---

## 🧠 AI Proctoring Features

- Face detection (present / not)
- Multiple face detection
- Head pose (looking away)
- Tab switch & focus loss
- Rule-based suspicion score

Each AI output is stored as an **event**, not a black-box decision.

---

## 🗂️ Data Tracked

- Exam attempts
- Browser events
- AI flags
- Timestamps
- Final suspicion score
- Proctor decision

Everything is auditable.

---

## 🛠 Tech Stack

### Frontend
- React + TypeScript
- Tailwind CSS
- React Router
- Zustand
- WebSockets
- Browser APIs

### Backend
- FastAPI
- JWT authentication
- SQLAlchemy
- PostgreSQL
- WebSockets

### AI
- OpenCV
- MediaPipe
- NumPy

---

## 🚀 How to Run

### Backend
```bash
uvicorn app.main:app --reload

---------------------------------------------------------------------------------------

# AI-Exam-Proctoring-Platform
“This is a online exam platform with AI-assisted proctoring. Instead of heavy video streaming or deep learning, it uses browser events + webcam snapshots + rule-based AI to detect suspicious behavior in real time. The focus is explainability, low cost, and clean system design.”

Key Points

• Built an AI-assisted online exam and proctoring platform using FastAPI and React
• Implemented real-time monitoring with WebSockets and browser behavior tracking
• Designed explainable AI proctoring using OpenCV and MediaPipe without video streaming
• Created rule-based suspicion scoring with full event timelines for auditability
• Applied role-based access control (RBAC) for students, proctors, and admins

User Roles & RBAC (Single App) Role	Responsibilities
1]Student	->Takes exam, monitored by AI
2]Proctor / Examiner ->	Creates exams, reviews flags
3]Admin -> Manages users & roles

Backend
fastapi – Build high-performance REST APIs for the exam and user management
uvicorn – ASGI server to run the FastAPI application
sqlalchemy – ORM for interacting with the PostgreSQL database
psycopg2 – PostgreSQL database driver for Python
alembic – Database migration and version control tool
python-jose – Create and verify JWT tokens for authentication
passlib[bcrypt] – Securely hash and verify user passwords
python-multipart – Handle form data and file uploads (exam files, images)
opencv-python – Capture and analyze webcam frames for proctoring
mediapipe – Face, eye, and head-pose detection for AI monitoring
numpy – Fast numerical computations for image and signal processing
scikit-learn – ML models for anomaly detection and behavior scoring
