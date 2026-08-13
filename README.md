# FaceTrack — AI-Based Face Recognition Attendance System


## Academic Project

FaceTrack is an academic project assigned by **JVM Maheta College**, affiliated with the **University of Mumbai**.

The project was developed as a practical implementation of concepts including:

* Full-stack web application development
* REST API development
* Database management
* Computer vision
* Facial recognition
* Desktop GUI development
* Cloud/backend deployment
* Software integration

### Institution

**JVM Maheta College**
Affiliated with **University of Mumbai**

### Project

**FaceTrack — AI-Based Face Recognition Attendance System**

The project combines a web-based attendance management system with a Python desktop face-recognition application to provide an automated approach to student attendance.

> This project is developed for academic and educational purposes.

FaceTrack is a full-stack **face recognition-based attendance management system** designed to automate student attendance using facial recognition.

The system consists of three main components:

1. **FaceTrack Frontend** — Web-based dashboard for managing students, attendance sessions, and reports.
2. **FaceTrack Backend** — API and database layer responsible for authentication, student data, face data, attendance records, and communication between the web application and desktop application.
3. **FaceTrack Desktop Application** — Windows GUI application built with Python and Tkinter that accesses the camera, recognizes registered students, and records attendance through the backend.

---

## Project Repositories

| Component           | Technology                          | Repository                                                              |
| ------------------- | ----------------------------------- | ----------------------------------------------------------------------- |
| Frontend            | React + Vite + TypeScript           | [FaceTrack Frontend](https://github.com/deepanshu045/FacetrackFrontend) |
| Backend             | Python + FastAPI                    | [FaceTrack Backend](https://github.com/deepanshu045/FacetrackBackend)   |
| Desktop Application | Python + Tkinter + Face Recognition | Windows `.exe` application                                              |

---

# Features

## Web Application

The FaceTrack web application provides a central interface for managing the attendance system.

### Student Management

* Register students.
* Store student information.
* Register and manage facial information.
* Manage student records.

### Attendance Management

* Create attendance sessions.
* Generate a camera access code for an attendance session.
* Allow the desktop recognition application to connect to the correct session.
* Monitor attendance activity.

### Reports

* View attendance records.
* Review student attendance.
* Generate attendance-related information and reports.

---

# Desktop Face Recognition Application

The desktop application is the component responsible for accessing the camera and recognizing students.

It is distributed as a Windows executable:

```text
FaceTrack.exe
```

The application provides a graphical interface using **Tkinter**, so users do not need to install Python or run commands manually.

### Recognition Workflow

1. The administrator/teacher starts an attendance session from the web application.
2. The web application generates a **camera access code**.
3. The user opens the FaceTrack desktop application.
4. The desktop application asks for the camera access code.
5. The code is sent to the backend for verification.
6. After successful verification, the desktop application accesses the computer's camera.
7. The application captures faces from the camera.
8. Captured faces are compared against registered student face data.
9. When a registered student is successfully recognized, the attendance information is sent to the backend.
10. The attendance record becomes available through the web application.

```text
Teacher / Admin
       │
       ▼
┌─────────────────────┐
│ FaceTrack Frontend  │
│                     │
│ Create Attendance   │
│ Session             │
└──────────┬──────────┘
           │
           │ Camera Access Code
           ▼
┌─────────────────────┐
│ FaceTrack Desktop   │
│                     │
│ Enter Code          │
│ Open Camera         │
│ Detect Face         │
│ Recognize Student   │
└──────────┬──────────┘
           │
           │ Attendance / API
           ▼
┌─────────────────────┐
│ FaceTrack Backend   │
│                     │
│ Verify Session      │
│ Student Data        │
│ Face Data           │
│ Attendance Records  │
└──────────┬──────────┘
           │
           ▼
        Database
           │
           ▼
┌─────────────────────┐
│ FaceTrack Frontend  │
│                     │
│ Attendance Reports  │
│ Student Records     │
└─────────────────────┘
```

---

# System Architecture

FaceTrack follows a client-server architecture.

### Frontend

The web frontend provides the user interface and communicates with the backend through APIs.

```text
React / TypeScript
        │
        │ HTTP API
        ▼
     Backend
```

### Backend

The backend acts as the central service responsible for:

* API endpoints
* Authentication
* Student information
* Face-related data
* Attendance sessions
* Attendance records
* Database communication
* Communication with the desktop application

### Desktop Application

The desktop application acts as the camera and face-recognition client.

```text
Camera
   │
   ▼
FaceTrack.exe
   │
   │ API
   ▼
Backend
   │
   ▼
Database
```

---

# Technologies Used

## Frontend

* React
* TypeScript
* Vite
* Tailwind CSS
* Lucide Icons
* REST API communication

## Backend

* Python
* FastAPI
* SQLAlchemy
* MySQL
* PyMySQL
* Docker
* Gunicorn / Uvicorn

## Desktop Application

* Python
* Tkinter
* OpenCV
* `face_recognition`
* dlib
* NumPy
* PyInstaller

## Database

FaceTrack uses a relational database to store application data such as:

* Students
* Attendance records
* Attendance sessions
* Face-related information
* Application data

---

# Repository Structure

## Frontend

```text
FacetrackFrontend/
│
├── src/
│   ├── components/
│   ├── pages/
│   └── ...
│
├── public/
├── package.json
├── vite.config.ts
├── .env.example
└── README.md
```

## Backend

```text
FacetrackBackend/
│
├── app/
├── certs/
├── tests/
├── Dockerfile
├── requirements.txt
├── .env.example
└── README.md
```

## Desktop Application

The desktop application is distributed as a compiled Windows executable:

```text
FaceTrack.exe
```

The executable contains the Python runtime and required application dependencies, allowing the end user to run the application without manually installing the Python environment.

---

# Running the Frontend

Clone the repository:

```bash
git clone https://github.com/deepanshu045/FacetrackFrontend.git
```

Enter the project directory:

```bash
cd FacetrackFrontend
```

Install dependencies:

```bash
npm install
```

Create your environment configuration from the provided example:

```text
.env.example
```

Configure the backend API URL according to your deployment.

Start the development server:

```bash
npm run dev
```

The frontend will then be available through the local Vite development server.

---

# Running the Backend

Clone the backend repository:

```bash
git clone https://github.com/deepanshu045/FacetrackBackend.git
```

Enter the project directory:

```bash
cd FacetrackBackend
```

Create a Python virtual environment:

```bash
python -m venv myenv
```

Activate it on Windows:

```powershell
myenv\Scripts\Activate.ps1
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Create the environment configuration using:

```text
.env.example
```

Configure the required database and application environment variables.

The backend can also be deployed using the included Docker configuration.

---

# Desktop Application

The FaceTrack desktop application is distributed as:

```text
FaceTrack.exe
```

### Requirements

The computer running the application should have:

* Windows
* Working webcam/camera
* Internet connection to communicate with the FaceTrack backend
* Permission to access the camera

Python does not need to be installed when using the compiled `.exe`.

### Usage

1. Start the FaceTrack web application.
2. Create an attendance session.
3. Copy the generated camera access code.
4. Open `FaceTrack.exe`.
5. Enter the camera access code.
6. Allow camera access if requested.
7. Position students in front of the camera.
8. The application detects and recognizes registered faces.
9. Recognized students are recorded as present.
10. View attendance information from the web application.

---

# Face Recognition Process

The desktop application uses computer vision and facial recognition to identify registered students.

The general process is:

```text
Camera Frame
     │
     ▼
Face Detection
     │
     ▼
Face Encoding
     │
     ▼
Compare With Registered Faces
     │
     ├── Match Found
     │      │
     │      ▼
     │   Identify Student
     │      │
     │      ▼
     │   Send Attendance
     │
     └── No Match
            │
            ▼
       Continue Scanning
```

This allows attendance to be recorded automatically without requiring students to manually enter their identity.

---

# Camera Access Code

The camera access code provides a connection between the web attendance session and the desktop recognition application.

The code helps ensure that the desktop application is connected to the intended attendance session before recognition begins.

```text
Web Application
      │
      │ Generate Code
      ▼
Attendance Session
      │
      │ Code
      ▼
FaceTrack.exe
      │
      │ Verify Code
      ▼
Backend
      │
      ▼
Camera Session
```

---

# Security Considerations

The application uses a backend-controlled workflow rather than allowing the desktop application to directly access the database.

The desktop application communicates with the backend API, while the backend handles database operations.

Sensitive configuration values such as:

* Database credentials
* API secrets
* Authentication credentials
* Private environment variables

should **not be committed to GitHub**.

Use environment variables and keep actual `.env` files out of version control.

The repositories include `.env.example` files to demonstrate the expected configuration without exposing actual secrets.

---

# Deployment

The FaceTrack system can be deployed as separate components.

```text
                    Internet
                       │
          ┌────────────┴────────────┐
          │                         │
          ▼                         ▼
   Web Frontend                Desktop Client
          │                         │
          │                         │
          └──────────┬──────────────┘
                     │
                     ▼
              FaceTrack Backend
                     │
                     ▼
                  MySQL
```

The frontend can be deployed as a web application, while the backend can be deployed as a containerized Python service.

The desktop application is distributed independently as a Windows executable.

---

# Advantages

* Automated attendance using face recognition
* Reduces manual attendance work
* Centralized student and attendance management
* Web-based administration
* Dedicated desktop camera application
* Session-based camera authorization
* Backend-controlled data management
* Attendance reports and records
* Windows executable for easy desktop deployment

---

# Limitations

Face recognition performance can depend on:

* Camera quality
* Lighting conditions
* Face angle
* Distance from the camera
* Image quality
* Registered face quality
* Recognition threshold

For reliable attendance, students should be properly registered and the camera should have adequate lighting and positioning.

---

# Future Improvements

Possible future improvements include:

* Liveness detection
* Anti-spoofing protection
* Multiple camera support
* Improved recognition accuracy
* Automatic camera/device discovery
* Real-time attendance dashboard
* Export reports to Excel/PDF
* Role-based access control
* Desktop application auto-update
* Improved offline handling
* Attendance notifications
* Advanced analytics

---

# Project Status

FaceTrack is an actively developed project consisting of a web frontend, backend API, database integration, and Windows desktop face-recognition application.

---

# Repositories

### Frontend

https://github.com/deepanshu045/FacetrackFrontend

### Backend

https://github.com/deepanshu045/FacetrackBackend

---

# Author

**Deepanshu**

GitHub:

https://github.com/deepanshu045

---
