````markdown
# 🧠 InterviewIQ — AI-Powered Technical Interview Platform

InterviewIQ is a full-stack AI-powered technical interview preparation platform designed to simulate real-world technical interviews.

The platform allows candidates to select an interview role, difficulty level, and interview type, then answer conceptual questions verbally or solve coding challenges directly in the browser. AI evaluates the responses and provides technical and confidence scores along with detailed performance insights.

---

## 🚀 Key Features

### 🎯 Customizable Interviews

Candidates can customize their interview experience based on:

- **Role**
  - MERN
  - Python
  - Data Science
- **Difficulty Level**
- **Interview Type**
  - Oral
  - Coding
  - Mixed

---

### 🎙️ Voice-Based Interview

InterviewIQ supports verbal answers for conceptual interview questions.

- Records candidate audio
- Uses **OpenAI Whisper** for Speech-to-Text
- Converts verbal responses into text
- Sends the transcription for AI-based evaluation

---

### 💻 Integrated Coding Environment

For coding-based interview questions, candidates can write and submit code directly inside the application.

- Integrated **Monaco Editor**
- Browser-based coding experience
- Question-specific coding challenges
- AI-based evaluation of submitted code

---

### 🤖 AI-Powered Question Generation

The application uses a dedicated Python AI microservice for interview intelligence.

The system dynamically generates interview questions based on:

- Selected role
- Difficulty level
- Interview type

**Ollama + Mistral** is used as the local LLM engine.

---

### 🧠 AI-Based Evaluation

Candidate responses are evaluated using AI.

The system analyzes:

- Verbal responses
- Technical understanding
- Code logic
- Relevance of answers
- Overall interview performance

The evaluation generates:

- **Technical Score**
- **Confidence Score**
- Feedback
- Performance insights

---

### 📊 Interview Analytics

Candidates can review their previous interview sessions and analyze their performance.

Features include:

- Session history
- Overall scores
- Question-wise performance
- Candidate submission vs. ideal implementation
- Performance charts
- Detailed session review

Analytics are visualized using **Chart.js**.

---

### 🔐 Secure Authentication

The application provides user authentication using:

- JWT (JSON Web Tokens)
- bcryptjs
- Protected routes
- User registration and login

---

# 🏗️ System Architecture

InterviewIQ follows a microservices-inspired architecture that separates the main application backend from AI-heavy processing.

```text
                    ┌─────────────────────┐
                    │       Frontend      │
                    │   React + Vite      │
                    │                     │
                    │ • Interview UI      │
                    │ • Voice Recording   │
                    │ • Monaco Editor     │
                    │ • Dashboard         │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      Backend        │
                    │   Node.js + Express │
                    │                     │
                    │ • Authentication    │
                    │ • REST APIs         │
                    │ • Session Handling  │
                    │ • Database Access   │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │     AI Service      │
                    │ Python + FastAPI    │
                    │                     │
                    │ • Question Gen.     │
                    │ • Transcription     │
                    │ • Evaluation        │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   Ollama + Mistral  │
                    │    Local LLM        │
                    └─────────────────────┘
````

---

# 🛠️ Technology Stack

## Frontend

| Technology       | Purpose                         |
| ---------------- | ------------------------------- |
| React            | User interface                  |
| Vite             | Frontend development/build tool |
| Redux Toolkit    | State management                |
| Tailwind CSS     | Styling                         |
| React Router DOM | Application routing             |
| Monaco Editor    | Coding environment              |
| Chart.js         | Performance visualization       |

---

## Backend

| Technology | Purpose                 |
| ---------- | ----------------------- |
| Node.js    | Backend runtime         |
| Express.js | REST API framework      |
| MongoDB    | Database                |
| Mongoose   | MongoDB object modeling |
| JWT        | Authentication          |
| bcryptjs   | Password hashing        |

---

## AI Microservice

| Technology     | Purpose            |
| -------------- | ------------------ |
| Python         | AI service runtime |
| FastAPI        | AI service API     |
| Ollama         | Local LLM runtime  |
| Mistral        | Language model     |
| OpenAI Whisper | Speech-to-text     |
| PyDub          | Audio processing   |
| FFmpeg         | Audio processing   |

---

# 📂 Project Structure

```text
InterviewIQ/
│
├── ai-service/
│   ├── main.py
│   └── requirements.txt
│
├── backend/
│   ├── config/
│   │   └── db.js
│   │
│   ├── controllers/
│   │   ├── sessionController.js
│   │   └── userController.js
│   │
│   ├── middleware/
│   │   ├── authMiddleware.js
│   │   ├── errorMiddleware.js
│   │   └── uploadMiddleware.js
│   │
│   ├── models/
│   │   ├── SessionModel.js
│   │   └── User.js
│   │
│   ├── routes/
│   │   ├── sessionRoutes.js
│   │   └── userRoutes.js
│   │
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── src/
│   │   ├── app/
│   │   │   └── store.js
│   │   │
│   │   ├── components/
│   │   │   ├── Header.jsx
│   │   │   ├── PrivateRoute.jsx
│   │   │   └── SessionCard.jsx
│   │   │
│   │   ├── features/
│   │   │   ├── auth/
│   │   │   └── sessions/
│   │   │
│   │   ├── hooks/
│   │   │   └── useSocket.js
│   │   │
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx
│   │   │   ├── InterviewRunner.jsx
│   │   │   ├── Login.jsx
│   │   │   ├── Profile.jsx
│   │   │   ├── Register.jsx
│   │   │   └── SessionReview.jsx
│   │   │
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   │
│   ├── package.json
│   └── vite.config.js
│
├── .gitignore
├── for-first-time.bat
├── start-all.bat
└── README.md
```

---

# 🔄 How InterviewIQ Works

```text
1. User Registration / Login
            ↓
2. Select Interview Role
            ↓
3. Select Difficulty & Interview Type
            ↓
4. AI Generates Interview Questions
            ↓
5. Candidate Answers
       ↙             ↘
  Voice Answer     Coding Answer
       ↓                ↓
   Whisper          Monaco Editor
       ↓                ↓
       └───────┬────────┘
               ↓
       AI Evaluation
               ↓
    Technical + Confidence
           Scores
               ↓
      Detailed Feedback
               ↓
       Session Analytics
```

---

# 🤖 AI Service

The AI service is implemented separately using **Python and FastAPI**.

It handles AI-intensive operations such as:

### Question Generation

```text
POST /generate-questions
```

Generates interview questions according to the selected interview configuration.

### Speech Transcription

```text
POST /transcribe
```

Converts recorded candidate audio into text using OpenAI Whisper.

### Response Evaluation

```text
POST /evaluate
```

Analyzes candidate answers/code and returns evaluation data including scores and feedback.

---

# 📊 Performance Evaluation

InterviewIQ provides structured performance evaluation based on the candidate's responses.

The platform provides:

* Technical Score
* Confidence Score
* Question-level evaluation
* Feedback
* Ideal implementation/reference
* Overall interview performance

This allows candidates to identify their strengths and areas that require improvement.

---

# 💻 Installation & Setup

## Prerequisites

Make sure the following are installed:

* Node.js v16+
* npm
* Python 3.9+
* pip
* MongoDB or MongoDB Atlas
* Ollama
* FFmpeg

---

## 1. Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/InterviewIQ.git
cd InterviewIQ
```

---

## 2. Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend` folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
NODE_ENV=development
```

Start the backend:

```bash
npm run server
```

---

## 3. AI Service Setup

Open a new terminal:

```bash
cd ai-service
```

Create a Python virtual environment:

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### macOS / Linux

```bash
python -m venv venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Make sure Ollama is installed and running.

Pull the Mistral model:

```bash
ollama pull mistral
```

Create the required `.env` configuration:

```env
AI_SERVICE_PORT=8000
OLLAMA_MODEL_NAME=mistral
```

Start the AI service:

```bash
uvicorn main:app --reload --port 8000
```

---

## 4. Frontend Setup

Open another terminal:

```bash
cd frontend
npm install
```

Create a `.env` file:

```env
VITE_API_URL=http://localhost:5000/api
```

Start the frontend:

```bash
npm run dev
```

The frontend will then be available through the local Vite development server.

---

# ⚡ Quick Start

For supported Windows environments, the project also includes:

```text
for-first-time.bat
start-all.bat
```

These batch files can be used to simplify the local setup and startup process.

---

# 🔐 Environment Variables

Do not commit sensitive credentials or API keys to GitHub.

Example:

```env
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret
```

Keep `.env` files inside `.gitignore`.

---

# 🎯 Use Cases

InterviewIQ can be used by:

* Students preparing for technical interviews
* Freshers preparing for placement interviews
* Developers practicing coding interviews
* Candidates preparing for MERN interviews
* Python developers preparing for technical interviews
* Data Science candidates preparing for interviews
* Candidates looking for structured interview feedback

---

# 💡 Problem Statement

Traditional interview preparation often relies on static question lists and does not provide personalized evaluation.

Candidates may know the correct answer but still need to improve their:

* Technical explanation
* Problem-solving approach
* Communication
* Confidence
* Coding implementation

InterviewIQ addresses this by providing an interactive interview environment with AI-powered question generation, response evaluation, scoring, and performance analytics.

---

# ✅ Solution

InterviewIQ combines:

**Interactive Interviews + AI Evaluation + Coding Environment + Voice Processing + Analytics**

into one platform.

This creates a more realistic and measurable interview preparation experience compared with simply practicing from static question lists.

---

# 🔮 Future Enhancements

Potential future improvements include:

* Resume-based interview generation
* More programming languages
* Real-time AI interviewer interaction
* Advanced communication analysis
* Facial expression analysis
* Personalized learning recommendations
* Recruiter / HR dashboard
* More interview domains and roles
* Multi-language interview support
* Advanced candidate comparison and analytics

---

# 🤝 Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch

```bash
git checkout -b feature/AmazingFeature
```

3. Commit your changes

```bash
git commit -m "Add AmazingFeature"
```

4. Push the branch

```bash
git push origin feature/AmazingFeature
```

5. Open a Pull Request

---

# 📄 License

This project is distributed under the MIT License.

```


