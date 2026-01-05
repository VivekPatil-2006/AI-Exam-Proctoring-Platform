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
