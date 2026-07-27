# AI Gym Coach - Setup & Deployment Guide

## 1. Project Overview & Location
The project has been cloned to **`E:\ai-gym-coach`**.

Directory structure:
- **`LandingPage/`**: Frontend landing page (`index.html`, `style.css`).
- **`MainApp/`**: Streamlit AI Web App with real-time pose estimation (MediaPipe & OpenCV), WebRTC streaming, and LLM Coaching (Groq API).
- **`venv/`**: Virtual environment with all installed dependencies.

---

## 2. Running Locally

### Step 1: Environment Setup
Create a `.env` file in `E:\ai-gym-coach\MainApp\.env` with your Groq API key:
```env
GROQ_API_KEY=your_groq_api_key_here
```
*(Get a free Groq API key from [https://console.groq.com](https://console.groq.com))*

### Step 2: Run the Main App
Open your terminal in `E:\ai-gym-coach` and run:
```powershell
.\venv\Scripts\Activate.ps1
cd MainApp
streamlit run main.py
```
The app will open automatically in your browser at `http://localhost:8501`.

### Step 3: Run the Landing Page
You can open `E:\ai-gym-coach\LandingPage\index.html` directly in any web browser, or use a local static server like Live Server.

---

## 3. How to Deploy

### Option A: Deploying Main App on Streamlit Community Cloud (Recommended)

1. **GitHub Setup**:
   - Push this repository to your GitHub account.

2. **Deploy on Streamlit Community Cloud**:
   - Go to [share.streamlit.io](https://share.streamlit.io/) and log in with GitHub.
   - Click **New app**.
   - Select your repository: `HEMANTH0425/AI_GYM_COACH`.
   - Branch: `main`.
   - Main file path: `MainApp/main.py`.

3. **Configure Environment Secrets**:
   - Before launching, click **Advanced settings...**.
   - Under **Secrets**, add your Groq API key:
     ```toml
     GROQ_API_KEY = "your-actual-groq-api-key"
     ```
   - Click **Save** and then **Deploy!**

---

### Option B: Deploying Landing Page

#### 1. Vercel / Netlify / GitHub Pages
- **GitHub Pages**:
  1. Go to repository **Settings** -> **Pages**.
  2. Select branch `main` and root `/LandingPage`.
  3. Click **Save**.

- **Vercel / Netlify**:
  1. Connect your repository to Vercel or Netlify.
  2. Set Root Directory to `LandingPage`.
  3. Click **Deploy**.
