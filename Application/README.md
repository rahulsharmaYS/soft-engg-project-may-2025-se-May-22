# Skillzy: Student–Teacher Learning Platform

## Overview
Skillzy is a web application developed as part of the **Software Engineering Project** for the **IIT Madras BS in Data Science and Applications** program.  
It is designed to help students (Age 8-14) learn, practice, and connect with teachers in a structured and engaging way.  

The application is built using latest **Vue.js 3** for the frontend and **FastAPI** for the backend. It uses **Celery** for background task scheduling and supports environment-based API keys for integrations.

---

##  Team Members
- Rahul Sharma (23f1001879)  
- Aarush Saxena (23f2005702)  
- Deepak Kumar Singh (21f1006490)  
- Kumar Rishabh (23f1000391)  
- Arya Chavan (21f1002763)  
- Nikhil Sai Kasireddy (21f3002651)  
- Gopu Vishal Reddy (21f2001548)  

---

## Tech Stack
- **FastAPI**: For backend APIs  
- **Vue.js (version 3) + Vite**: For frontend UI  
- **SQLAlchemy**: For database management  
- **HTML/CSS and DotLottie**: For animations & styling  
- **Celery + Redis**: For background jobs and scheduling  
- **npm**: For managing frontend dependencies  
- **Python ~3.13.0**: For backend environment  
- **Open AI**: For chatbot integration
---

## Setup Instructions

### Step 1: Clone the Project
1. Clone the project repository and navigate to the project root directory (where Backend and frontend folders are present:
    ```bash
    git clone <https://github.com/rahulsharmaYS/skillzy>                  # will update once grades are out
    ```


### Step 2: Install Backend Dependencies
1. Navigate to the backend directory and install the necessary Python packages:
    ```bash
    cd Backend
    pip install -r requirements.txt

    ```

### Step 3: Install Frontend Dependencies
1. Navigate to the frontend directory and install Node.js dependencies:
    ```bash
    cd frontend/SE-project
    npm install    
    ```

### Step 4: Make sure your redis is working
1. Navigate to the Backend directory in your WSL and run below command to start your redis-server:
    ```bash
    redis-server
    ```
2. (OPTIONAL) To test your Redis server via pinging, it should return "PONG" response:
    ```bash
    redis-cli ping
    ```
---

## Running the Application

Open your IDE (e.g., VS Code) and split the terminal into **4 terminals**. Run the following commands in each:

### Terminal 1 → Backend API
```bash
cd <your-root-dir>/Backend/
uvicorn main:app --reload
```

### Terminal 2 → Frontend
```bash
cd <your-root-dir>frontend/SE-project
npm run dev
```

### Terminal 3 → Celery Worker
```bash
cd <your-root-dir>Backend/
celery -A celery_app worker --loglevel=debug
```

### Terminal 4 → Celery Beat
```bash
cd <your-root-dir>/Backend/
celery -A celery_app beat --loglevel=debug
```

## Environment Variables to run AI ChatBot
1. Inside the "Backend/" dir, in .env file, add your own OPENAI API key. Example:
```bash
OPENAI_API_KEY=sk-proj-qwertasdfzxc.........abcd
```

---

## ⚠️ Disclaimer
Ensure that you add valid API keys in the `.env` file.  
Without them, the application may not function properly.

---

 ## 🎉 That’s it!  
 Our **Skillzy app** should now be up and running :)
 
 ⭐ **If you like our app and appreciate the hard work, don’t forget to star this repo!** ⭐  
 
 It means a lot to us and our team ❤️


MIT License

Copyright (c) 2025 Skillzy Team
- Rahul Sharma (23f1001879)
- Aarush Saxena (23f2005702)
- Deepak Kumar Singh (21f1006490)
- Kumar Rishabh (23f1000391)
- Arya Chavan (21f1002763)
- Nikhil Sai Kasireddy (21f3002651)
- Gopu Vishal Reddy (21f2001548)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
