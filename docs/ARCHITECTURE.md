# Hirely – Architecture Overview

## 1. Frontend

- React + TypeScript SPA
- React Router for routing
- Redux Toolkit for global state (auth, user, jobs, applications)
- Axios for API calls with interceptors for JWT
- Socket.io client for real‑time updates

## 2. Backend

- Node.js + Express REST API
- Mongoose for MongoDB models
- Auth:
  - JWT access + refresh tokens
  - Role‑based authorization middleware
- File uploads (resumes, avatars) to cloud storage

## 3. Database

- MongoDB with main collections:
  - `users`, `jobs`, `applications`, `resumes`
- Indexes on email, job title, location, createdAt
- See `docs/db-schema.md` for details.

## 4. Realtime & Notifications

- Socket.io namespace for authenticated users
- Events:
  - `applicationStatusChanged`
  - `newApplicationReceived`
- Notifications stored in DB (for later history view).

## 5. DevOps

- `.env` and `.env.example` under `backend/`
- Docker for backend, frontend, and MongoDB
- Git branching:
  - `main`: stable
  - `develop`: integration
  - `feature/*`: feature branches