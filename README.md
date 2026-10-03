# 🧠 InterviewIQ — AI-Powered Technical Interview Platform

InterviewIQ is a full-stack AI-powered technical interview preparation platform designed to simulate real-world technical interviews.

The platform allows candidates to select an interview role, difficulty level, and interview type, then answer conceptual questions verbally or solve coding challenges directly in the browser. AI evaluates the responses and provides technical and confidence scores along with detailed performance insights.

---

## ✨ Key Features

### 🎯 Customizable Interviews
- Select interview role:
  - MERN
  - Python
  - Data Science
- Choose difficulty level.
- Select interview type:
  - Oral
  - Coding
  - Mixed

### 🎤 Voice-Based Interview
- Candidates can answer questions using voice.
- Audio responses are converted into text using OpenAI Whisper.
- Transcribed responses are evaluated by the AI service.

### 💻 Online Coding Environment
- Built-in Monaco Editor for coding questions.
- Candidates can write and review code directly in the browser.
- Supports coding-based technical interview practice.

### 🤖 AI-Powered Question Generation
- AI generates interview questions based on:
  - Selected role
  - Difficulty
  - Interview type
- Ollama with Mistral is used for AI-powered question generation.

### 📊 AI Evaluation
The AI service evaluates candidate responses and provides:
- Technical Score
- Confidence Score
- Question-wise evaluation
- Performance insights

### 📈 Interview Analytics
- Session history
- Overall performance scores
- Question-wise performance
- User submission vs ideal implementation
- Interactive charts using Chart.js

### 🔐 Authentication
- User registration and login
- JWT-based authentication
- Password hashing using bcryptjs

---

## 🛠️ Tech Stack

### Frontend
- React
- Vite
- Redux Toolkit
- Tailwind CSS
- React Router DOM
- Monaco Editor
- Chart.js
- React-Chartjs-2

### Backend
- Node.js
- Express.js
- MongoDB
- Mongoose
- JWT
- bcryptjs

### AI Service
- Python
- FastAPI
- Ollama
- Mistral
- OpenAI Whisper
- PyDub

---

## 📐 Architecture

```text
                ┌─────────────────────────┐
                │     React Frontend      │
                │       Vite + Redux      │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │    Node.js Backend      │
                │     Express + MongoDB   │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │      Python AI Service  │
                │        FastAPI          │
                └────────────┬────────────┘
                             │
                             ▼
                ┌─────────────────────────┐
                │     Ollama + Mistral    │
                │      AI Processing      │
                └─────────────────────────┘

````

---

## 🔄 How It Works

1. User registers or logs into InterviewIQ.
2. User selects the interview role, difficulty, and interview type.
3. The backend communicates with the AI service to generate interview questions.
4. User answers questions through voice or coding.
5. Voice responses are transcribed using OpenAI Whisper.
6. The AI service evaluates the responses.
7. Technical and confidence scores are generated.
8. Results are stored and displayed through the dashboard.
9. Users can review previous interview sessions and question-wise performance.

---

## 📁 Project Structure

```text
InterviewIQ/
│
├── frontend/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── ...
│
├── backend/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── server.js
│   ├── package.json
│   └── ...
│
├── ai-service/
│   ├── main.py
│   ├── requirements.txt
│   └── ...
│
├── .gitignore
├── README.md
└── ...
```

---

## 🚀 Getting Started

### Prerequisites

Make sure the following are installed:

* Node.js v16+
* Python 3.9+
* MongoDB
* Ollama
* FFmpeg

---

## ⚙️ Backend Setup

Open a terminal and run:

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

## 🤖 AI Service Setup

Open another terminal:

```bash
cd ai-service
```

Create and activate a virtual environment:

```bash
python -m venv venv
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Create a `.env` file:

```env
AI_SERVICE_PORT=8000
OLLAMA_MODEL_NAME=mistral
```

Start the AI service:

```bash
uvicorn main:app --reload --port 8000
```

---

## 🌐 Frontend Setup

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

The frontend will run on the local Vite development server.

---

## 🔗 AI Service Endpoints

The AI service provides functionality for:

```text
/generate-questions
/transcribe
/evaluate
```

These endpoints are used by the backend to communicate with the AI service for question generation, voice transcription, and response evaluation.

---

## 📊 Performance & Analytics

InterviewIQ provides an analytics dashboard where users can review:

* Overall interview scores
* Technical performance
* Confidence score
* Question-wise evaluation
* Previous interview sessions
* Coding submissions
* Performance trends

---

## 🔮 Future Enhancements

* Real-time AI interview conversations
* More programming languages
* Resume-based interview generation
* Advanced candidate performance analytics
* Improved speech and confidence analysis
* Interview recommendations based on previous performance

---

## 🤝 Contributing

Contributions, suggestions, and improvements are welcome.

To contribute:

1. Fork the repository.
2. Create a new branch.
3. Make your changes.
4. Commit your changes.
5. Create a pull request.

---

## 📄 License

This project is licensed under the MIT License.

```
```
