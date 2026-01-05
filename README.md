# AI-Exam-Proctoring-Platform
“This is a online exam platform with AI-assisted proctoring. Instead of heavy video streaming or deep learning, it uses browser events + webcam snapshots + rule-based AI to detect suspicious behavior in real time. The focus is explainability, low cost, and clean system design.”

Key Points

• Built an AI-assisted online exam platform with real-time proctoring using FastAPI and React
• Designed explainable AI rules for detecting suspicious behavior using OpenCV and MediaPipe
• Implemented WebSocket-based live monitoring and role-based dashboards
• Focused on low-cost, interpretable AI instead of heavy video streaming

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
