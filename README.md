# 🤖 Personal Data Assistant Chatbot

Welcome to your own **PDF-powered AI Chatbot**! This project helps you build a smart, document-aware chatbot using Flask, LangChain, and modern LLMs. Upload a PDF, ask questions, and get instant, context-aware answers—all through a beautiful web interface.

---

## 🌟 Features
- **Chat with your PDFs**: Upload any PDF and ask questions about its content.
- **Modern UI**: Clean, responsive frontend with light/dark mode.
- **Flexible LLM Backend**: Use IBM WatsonX or Hugging Face models.
- **Fast & Private**: All processing happens locally or in your own cloud.
- **Easy Deployment**: Run locally or with Docker in minutes.

---

## 📋 Table of Contents
- [Getting Started](#getting-started)
- [How It Works](#how-it-works)
- [Running the Application](#running-the-application)
- [Docker Deployment](#docker-deployment)
- [Switching to Hugging Face](#switching-to-hugging-face)
- [Project Structure](#project-structure)
- [License](#license)

---

## 🚀 Getting Started

### Prerequisites
- Python 3.x
- `pip` and `virtualenv`
- `git`

### Installation
```bash
# Clone the repository
$ git clone https://github.com/Garbii1/personal-data-assistant-chatbot.git
$ cd personal-data-assistant-chatbot/build_chatbot_for_your_data

# Create and activate a virtual environment
$ pip install virtualenv
$ virtualenv my_env
# On Windows:
$ my_env\Scripts\activate
# On macOS/Linux:
$ source my_env/bin/activate

# Install dependencies
$ pip install -r requirements.txt
$ pip install langchain-community
```

---

## ⚙️ How It Works

### 🖥️ Frontend
- **`index.html`**: Chat interface layout
- **`static/style.css`**: Modern, responsive styles (light/dark mode)
- **`static/script.js`**: Handles chat, file upload, and UI events

### 🧠 Backend
- **`worker.py`**: Handles PDF processing, embeddings, and LLM queries
- **`server.py`**: Flask server, API endpoints, and file handling

#### Main Flow
1. **Upload PDF** → Processed & split into chunks
2. **Embeddings** → Chunks stored in a vector database (Chroma)
3. **Ask Questions** → LLM retrieves relevant info and answers

---

## ▶️ Running the Application
```bash
$ python server.py
```
Visit [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser. Upload a PDF and start chatting!

---

## 🐳 Docker Deployment
```bash
# Build the Docker image
$ docker build . -t build_chatbot_for_your_data

# Run the container
$ docker run -p 8000:8000 build_chatbot_for_your_data
```
Access at [http://127.0.0.1:8000](http://127.0.0.1:8000).

---

## ✨ Switching to Hugging Face LLM
1. Install extra dependencies:
   ```bash
   pip install langchain==0.1.17 huggingface-hub==0.23.4
   ```
2. Get your Hugging Face API key from [huggingface.co](https://huggingface.co/settings/tokens)
3. Edit `worker.py`:
   - Replace the `init_llm()` function as shown in the code comments
   - Set your API key and desired model (e.g., `mistralai/Mistral-7B-Instruct-v0.3`)

---

## 📁 Project Structure
```
personal-data-assistant-chatbot/
├── build_chatbot_for_your_data/
│   ├── Dockerfile
│   ├── requirements.txt
│   ├── server.py
│   ├── worker.py
│   ├── static/
│   │   ├── script.js
│   │   └── style.css
│   └── templates/
│       └── index.html
├── my_env/ (virtual environment)
└── README.md
```

---

## 📄 License
This project is licensed under the MIT License. See the [LICENSE](build_chatbot_for_your_data/LICENSE) file for details.

---

> **Made with ❤️ by Garbii1**