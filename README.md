# 🗳️ AI-Powered Voter Verification System

![Python](https://img.shields.io/badge/Python-3.6%2B-blue?logo=python&logoColor=white)  
![Flask](https://img.shields.io/badge/Flask-Backend-lightgrey?logo=flask&logoColor=white)  
![HTML5](https://img.shields.io/badge/HTML5-Frontend-orange?logo=html5&logoColor=white)  
![CSS3](https://img.shields.io/badge/CSS3-Styles-blue?logo=css3&logoColor=white)  
![JavaScript](https://img.shields.io/badge/JavaScript-Frontend-yellow?logo=javascript&logoColor=white)  
![Gemini API](https://img.shields.io/badge/Gemini-API-green?logo=google&logoColor=white)  
![License](https://img.shields.io/badge/License-Educational-purple)  

An **AI-powered system** designed to streamline and secure the voter authentication process.  
It uses a **full-stack approach** with a lightweight Python backend and a single-file HTML, CSS, and JavaScript frontend.  
The core of the verification is handled by a **multimodal model from the Gemini API**, which performs **two-factor authentication**: document analysis and live facial recognition.

---

## ✨ Features
- **Two-Factor Verification**: Authenticates voters by comparing their uploaded Voter ID with a live photo captured via webcam.  
- **AI-Driven Document Analysis**: Uses the Gemini API for OCR to extract details like voter name and ID from the voter card.  
- **Facial Recognition**: Matches the document photo with the live capture securely and accurately.  
- **Fraud Detection**: Detects tampering in voter IDs (e.g., inconsistent text or image manipulation).  
- **User-Friendly Interface**: A clean, single-page web UI for uploads and photo capture.  
- **Scalable Architecture**: Simple client-server model that is easy to deploy and scale.  

---

## 🚀 How It Works
The system operates on a **client-server architecture**:

1. **Frontend (index.html):**  
   - User uploads a voter ID and captures a live photo using the webcam.  

2. **API Call:**  
   - Both images are sent as Base64-encoded data to the backend via a POST request.  

3. **Backend (app.py):**  
   - Flask backend receives the images, decodes them, and sends them to the Gemini API as a multimodal request.  
   - The API responds with verification status, voter details, and decision reasoning.  

4. **Frontend Display:**  
   - Results are shown in real-time, indicating **success** ✅ or **failure** ❌.  

---

## 🛠️ Setup and Installation

### Prerequisites
- Python 3.6 or higher  
- `pip` (Python package manager)  
- An API key from **Google AI Studio (Gemini API)**  

---

### Backend Setup (`app.py`)

1. **Install Dependencies**  
   ```bash
   pip install Flask flask-cors requests

## 🔑 Get Your API Key

1. Go to **Google AI Studio**.  
2. Generate a new API key for your project.  
3. Open `app.py` and replace:  
   ```python
   OPENAI_API_KEY = "YOUR_API_KEY_HERE"
python app.py

## 💻 Frontend Setup (`index.html`)

- The frontend is a **single HTML file**.  
- Open `index.html` in a modern web browser (Chrome, Firefox, etc.).  

⚠️ Note: Browser security may block webcam/API access if opened directly.  
Run it via a **local server** instead:  

```bash
python -m http.server 8000

├── app.py           # Flask backend API
├── index.html       # Frontend UI
├── README.md        # Project documentation
└── ...other files...




