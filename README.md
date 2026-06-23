# 🏋️ AI Real-Time Gym Coach

An intelligent fitness assistant that uses AI-powered pose detection and computer vision to analyze workouts in real time. The system detects body posture, counts repetitions, tracks sets, and provides instant voice coaching through a live webcam interface.

---

## 🚀 Features

* **Real-Time Pose Detection** — Uses MediaPipe to track 33 body landmarks through a webcam
* **5 Exercise Support** — Squats, Push-ups, Bicep Curls, Shoulder Press, and Lunges
* **Automatic Rep & Set Counting** — Tracks workout progress by analyzing joint angles
* **AI Voice Coaching** — Generates personalized fitness feedback using Groq LLM
* **Live Pose Overlay** — Displays skeleton tracking on the video feed
* **Exercise Form Analysis** — Detects posture and movement mistakes in real time
* **Workout History Tracking** — Stores exercise performance and session statistics
* **User Authentication** — Individual user accounts with isolated workout data
* **Interactive Dashboard** — Simple and responsive Streamlit interface

---

# ⚠️ Important Requirement

### Python Version Compatibility

This project requires **Python 3.11 or below**.

✅ Recommended: **Python 3.11**

❌ Python 3.12, 3.13, and 3.14 may cause compatibility issues with MediaPipe and Streamlit-WebRTC dependencies.

Check your Python version:

```bash
python --version
```

---

## 🛠️ Tech Stack

| Technology       | Purpose                         |
| ---------------- | ------------------------------- |
| Python           | Core Programming Language       |
| Streamlit        | Web Application Framework       |
| MediaPipe        | Pose Detection                  |
| OpenCV           | Computer Vision Processing      |
| Streamlit-WebRTC | Live Webcam Streaming           |
| Groq API         | AI Coaching Feedback            |
| gTTS             | Text-to-Speech                  |
| SQLite           | Workout Data Storage            |
| Python Dotenv    | Environment Variable Management |

---

## 📁 Project Structure

```text
AI-GYM-Trainer/
│
├── main.py
├── requirements.txt
├── packages.txt
├── Dockerfile
├── data.db
│
├── static/
│   └── style.css
│
├── ml_models/
│   └── pose_landmarker_full.task
│
├── detectors/
│   ├── squat.py
│   ├── pushup.py
│   ├── biceps_curl.py
│   ├── shoulder_press.py
│   └── lunges.py
│
└── services/
    ├── auth/
    ├── coaching/
    ├── config/
    ├── persistence/
    ├── state/
    ├── tracking/
    ├── ui/
    └── vision/
```

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/asifkhan2303/AI-GYM-Trainer.git
cd AI-GYM-Trainer
```

---

### 2️⃣ Create a Python 3.11 Virtual Environment

#### Windows

```bash
py -3.11 -m venv venv311
venv311\Scripts\activate
```

#### Linux / macOS

```bash
python3.11 -m venv venv311
source venv311/bin/activate
```

---

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

---

### 4️⃣ Configure Environment Variables

Create a `.env` file in the project root:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Get a free API key from:

https://console.groq.com

---

### 5️⃣ Run the Application

```bash
streamlit run main.py
```

After startup:

```text
Local URL: http://localhost:8501
```

Open the URL in your browser and allow camera access when prompted.

---

## 🔑 Environment Variables

| Variable     | Description                  | Required |
| ------------ | ---------------------------- | -------- |
| GROQ_API_KEY | Groq API Key for AI coaching | ✅ Yes    |

---

## 📊 Supported Exercises

| Exercise       | Metrics Tracked               |
| -------------- | ----------------------------- |
| Squats         | Knee Angle, Back Angle, Depth |
| Push-Ups       | Elbow Angle, Body Alignment   |
| Bicep Curls    | Elbow Angle, Swing Detection  |
| Shoulder Press | Arm Extension, Back Position  |
| Lunges         | Knee Angle, Balance Tracking  |

---

## 🗄️ Database

Workout data is stored using SQLite.

### Users Table

Stores:

* Username
* Account creation timestamp

### Exercise History Table

Stores:

* Exercise Name
* Repetitions
* Sets
* Duration
* Session Date

Features:

* Per-user workout history
* Automatic updates for same-day exercise entries
* Persistent storage across sessions

---

## 🚀 Deployment

### Streamlit Community Cloud

1. Push project to GitHub
2. Visit https://share.streamlit.io
3. Connect repository
4. Add `GROQ_API_KEY` to Secrets
5. Deploy

---

### Docker

Build image:

```bash
docker build -t ai-gym-trainer .
```

Run container:

```bash
docker run -p 7860:7860 ai-gym-trainer
```

---

## 📦 Requirements

```text
streamlit>=1.40.0
streamlit-webrtc==0.47.1
tornado==6.2
numpy==1.26.4
mediapipe==0.10.35
opencv-python-headless==4.8.0.76
pandas==2.2.3
groq>=0.12.0
gtts==2.5.3
python-dotenv==1.2.2
```

---

## 👨‍💻 Author

### MOHD ASIF KHAN

* GitHub: https://github.com/asifkhan2303

---

## 📄 License

This project is licensed under the MIT License.

Feel free to fork, modify, and contribute.
