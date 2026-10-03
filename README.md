# 🧠 InterviewIQ — AI-Powered Technical Interview Platform

A full-stack application designed to simulate real-world technical interviews. InterviewIQ allows users to practice conceptual and coding questions, answer verbally or write code, and receive AI-based feedback on their performance.

## ✨ Key Features

* **Customizable Interviews**: Select Role (MERN, Python, Data Science), Difficulty Level, and Interview Type (Oral, Coding, or Mixed).

* **Hybrid Input System**:
  * **🎙️ Voice Response**: Uses **OpenAI Whisper** to transcribe verbal answers for conceptual questions.
  * **💻 Code Editor**: Integrated **Monaco Editor** for solving coding challenges directly in the browser.

* **AI-Powered Interview System**:
  * **Question Generation**: Generates interview questions based on the selected role, difficulty, and interview type using **Ollama (Mistral)**.
  * **AI Evaluation**: Evaluates verbal answers and submitted code to provide a **Technical Score**, **Confidence Score**, and feedback.

* **Interview Analytics**:
  * Session history with overall scores.
  * Question-wise performance breakdown.
  * User submission vs. ideal implementation.
  * Performance charts using **Chart.js**.

* **Secure Authentication**:
  * User registration and login.
  * JWT-based authentication.
  * Password hashing using **bcryptjs**.

---

## 🛠️ Tech Stack

### Frontend

* **Framework**: React (Vite)
* **State Management**: Redux Toolkit
* **Styling**: Tailwind CSS
* **Editor**: `@monaco-editor/react`
* **Visualization**: Chart.js / React-Chartjs-2
* **Routing**: React Router DOM

### Backend

* **Runtime**: Node.js
* **Framework**: Express.js
* **Database**: MongoDB (Mongoose)
* **Authentication**: JWT & bcryptjs

### AI Service

* **Runtime**: Python 3.9+
* **Framework**: FastAPI
* **LLM**: Ollama (Mistral)
* **Speech-to-Text**: OpenAI Whisper (`base.en`)
* **Audio Processing**: PyDub / FFmpeg

---

## 🚀 Getting Started

### Prerequisites

1. **Node.js** (v16+) and **npm**
2. **Python** (v3.9+) and **pip**
3. **MongoDB** — Local instance or MongoDB Atlas
4. **Ollama** — Installed and running locally
5. **FFmpeg** — Required for audio processing

### 1. Clone the Repository

```bash
git clone https://github.com/anishujama/InterviewIQ.git
cd InterviewIQ
