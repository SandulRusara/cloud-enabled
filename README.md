# Cloud Enabled Deployment In Action with AWS

This repository contains four projects:

- course-service (Spring Boot + MySQL)
- student-service (Spring Boot + MongoDB)
- media-service (Spring Boot + Local file storage, can be extended to S3/MinIO)
- frontend-app (React + TypeScript)

## Backend Services

### 1. course-service
- Entity: Course(id, name, duration)
- Endpoints:
  - GET /courses
  - GET /courses/{id}
  - POST /courses
  - DELETE /courses/{id}
- Default port: 8081
- Configure MySQL settings

### 2. student-service
- Document: Student(registrationNumber, fullName, address, contact, email)
- Endpoints:
  - GET /students
  - GET /students/{id}
  - POST /students
  - DELETE /students/{id}
- Default port: 8082
- Configure MongoDB settings

### 3. media-service
- Resource: files
- Endpoints:
  - POST /files (multipart/form-data: file)
  - GET /files (list)
  - GET /files/{id} (fetch)
  - DELETE /files/{id} (delete)
- Default port: 8083
- Uses local disk storage at `./data/media` by default (override with env var `MEDIA_STORAGE_DIR`).

## Frontend (frontend-app)
- React + TypeScript + MUI + Axios + Vite app with 3 sections: Courses, Students, Media
- Scripts:
  - npm run dev (Vite dev server)
  - npm run build (TypeScript build + Vite build)
  - npm run preview (Preview built app)

## Build

- Backend: run `mvn -q -e -DskipTests package` at repo root to build services.
- Frontend: run `npm install` then `npm run dev` inside `frontend-app`.




# Cloud-Enabled Deployment in Action with GCP

This repository demonstrates a **cloud-ready microservices system** deployed on **Google Cloud Platform (GCP)**, consisting of four independent projects:

- **course-service** → Spring Boot + MySQL
- **student-service** → Spring Boot + MongoDB
- **media-service** → Spring Boot + Local / Cloud (GCS / MinIO) Storage
- **frontend-app** → React + TypeScript (Vite + MUI)

---

## Backend Services

### 1. Course Service (`course-service`)
- **Entity:** `Course(id, name, duration)`
- **Endpoints:**
  - `GET /courses` – List all courses
  - `GET /courses/{id}` – Get course by ID
  - `POST /courses` – Create new course
  - `DELETE /courses/{id}` – Delete course
- **Port:** `8081`
- **Configuration:** Update **Cloud SQL (MySQL)** credentials in `application.properties`

---

### 2. Student Service (`student-service`)
- **Document:** `Student(registrationNumber, fullName, address, contact, email)`
- **Endpoints:**
  - `GET /students` – List all students
  - `GET /students/{id}` – Get student by ID
  - `POST /students` – Register new student
  - `DELETE /students/{id}` – Delete student
- **Port:** `8082`
- **Configuration:** Update **MongoDB (Atlas or GCP VM)** connection in `application.properties`

---

### 3. Media Service (`media-service`)
- **Resource:** File storage API
- **Endpoints:**
  - `POST /files` – Upload file (`multipart/form-data`)
  - `GET /files` – List all uploaded files
  - `GET /files/{id}` – Fetch file by ID
  - `DELETE /files/{id}` – Delete file
- **Port:** `8083`
- **Storage:**
  - Default → Local disk `./data/media`
  - Override with environment variable → `MEDIA_STORAGE_DIR`
  - Extendable → **Google Cloud Storage (GCS)** or MinIO backend

---

## Frontend App (`frontend-app`)
A modern **React + TypeScript** frontend powered by **Vite**, **Material UI**, and **Axios**.
- **Sections:** Courses | Students | Media
- **Scripts:**
  - `npm run dev` → Start development server
  - `npm run build` → Build production bundle
  - `npm run preview` → Preview production build

---

## Project Demo Video
You can watch the demo here:  
[Watch on Google Drive](https://drive.google.com/drive/folders/1mSjgTxyEjO0e0cS-WyBdkq9xGCUNvRi_?usp=sharing)


## Build & Run

### Backend Services
```bash
# From repo root
mvn -q -e -DskipTests package



