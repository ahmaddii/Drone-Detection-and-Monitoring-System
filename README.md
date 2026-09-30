# Real-Time AI Drone Detection & Monitoring System

![Drone Detection Demo](demo8.mp4_screenshot_14.10.2025.png)

## 📌 Overview
A real-time AI-based drone detection and monitoring system designed to identify and track unauthorized UAVs (drones). Built using a custom-trained **YOLOv8** object detection model, this project is capable of high-accuracy real-time inference on video feeds to mitigate security risks.

The system features two main ways to run and interact:
1. **Real-Time CLI / GUI Popup**: For quick, low-latency video inference using OpenCV.
2. **Full-Stack Web Application**: A robust Python/Flask backend integrated with a React.js dashboard for monitoring, uploading feeds, and managing detection logs.

## 🚀 Tech Stack
- **AI & Computer Vision**: YOLOv8 (Ultralytics), PyTorch, OpenCV
- **Backend**: Python, Flask
- **Frontend**: React.js, JavaScript, HTML/CSS
- **Environment Tools**: Node.js, npm, Python `venv`

## 📁 Project Structure
- `backend/`: Contains the Flask API and YOLOv8 inference logic (`app.py`).
- `frontend/`: Contains the React.js web dashboard.
- `runs/`: Contains the trained YOLOv8 model weights (e.g., `best.pt` in `runs/detect/train2/weights/`).
- `dataset/`: Configurations and datasets used for training the model.

---

## 🛠️ Installation & Setup

### Prerequisites
- **Python 3.8+**
- **Node.js & npm**

### 1. Setup the Backend (AI & API)
Navigate to the `backend` directory and set up the Python virtual environment:
```bash
cd backend

# Create and activate virtual environment (if not already created)
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt  # Or install flask & ultralytics manually
```

### 2. Setup the Frontend (React Dashboard)
Navigate to the `frontend` directory and install the Node dependencies:
```bash
cd frontend
npm install
```

---

## 💻 Usage Instructions

### Option 1: Quick Real-Time Inference (Command Line)
If you just want to see the AI detect drones in real-time via a popup window, run this command from the **root project directory** (ensure your virtual environment is activated):

```bash
yolo predict model=runs/detect/train2/weights/best.pt source=drone_demo4.mp4 show=True
```
*Note: You can replace `drone_demo4.mp4` with any of the demo video files in the root folder.*

### Option 2: Run the Full-Stack Web Dashboard
To run the full application, you will need two terminal windows open.

**Terminal 1: Start the Backend**
```bash
cd backend
source venv/bin/activate
python app.py
```
*(The backend will run on `http://localhost:5000`)*

**Terminal 2: Start the Frontend**
```bash
cd frontend
npm start
```
*(The frontend will open automatically in your browser at `http://localhost:3000`)*

---

## 🎯 Objectives
- **Detect and track** drones in real time using AI.
- **Alert authorities** when drones are detected via the dashboard.
- **Provide a scalable architecture** utilizing modern web technologies and state-of-the-art computer vision models.
