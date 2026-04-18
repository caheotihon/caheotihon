# T-Edu

T-Edu is an AI-assisted quiz and exam learning platform built for creating, sharing, taking, and reviewing exams in one place.

## Overview

This repository contains the full T-Edu system:

- `quiz-react`: React + Vite frontend
- `quiz-backend`: Express + MongoDB backend
- `docs`: architecture, class, and sequence diagrams

The platform supports both learners and creators. Users can discover public exams, take timed attempts, review results, study with flashcards, manage personal workspaces, and generate exams with AI from prompts or uploaded files. Admin users can moderate exams, manage reports, monitor users, and review AI usage.

## Key Features

- User authentication with email/password and Google login
- Public exam discovery and detail pages
- Timed exam attempts with history and result review
- Flashcard mode for reinforcement learning
- Personal dashboard, favorites, and profile management
- Exam authoring workspace for manual and AI-assisted creation
- AI exam generation from prompt, file upload, and analysis tasks
- Channel and follow flow for creator-centered sharing
- Admin dashboard for moderation, reports, users, and AI usage
- Real-time features via Socket.IO

## Tech Stack

### Frontend

- React 18
- Vite
- React Router
- Tailwind CSS
- Axios
- Socket.IO Client

### Backend

- Node.js
- Express 5
- MongoDB + Mongoose
- JWT authentication
- Multer for uploads
- Nodemailer
- Socket.IO
- Gemini and Groq integrations

## Project Structure

```text
T-Edu/
|-- docs/
|   |-- architecture-system.puml
|   |-- architecture.puml
|   |-- class-diagram.puml
|   `-- sequence-usecases.puml
|-- quiz-backend/
|   |-- src/
|   `-- package.json
|-- quiz-react/
|   |-- src/
|   `-- package.json
|-- docker-compose.yml
`-- README.md
```

## Getting Started

### Prerequisites

- Node.js 18+
- npm
- MongoDB

### Run locally

Frontend:

```bash
cd quiz-react
npm install
npm run dev
```

Backend:

```bash
cd quiz-backend
npm install
npm run dev
```

Default local endpoints:

- Frontend: `http://localhost:5173`
- Backend: `http://localhost:5000`
- API base: `http://localhost:5000/api/v1`

### Run with Docker

```bash
docker compose up --build
```

## Environment Variables

Create local environment files before running the app.

Frontend (`quiz-react/.env`) should define values such as:

```env
VITE_API_URL=http://localhost:5000/api/v1
VITE_GOOGLE_CLIENT_ID=your_google_client_id
```

Backend (`quiz-backend/.env`) should define values such as:

```env
NODE_ENV=development
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/t-edu-db
JWT_SECRET=your_jwt_secret
GEMINI_API_KEY=your_gemini_api_key
GROQ_API_KEY=your_groq_api_key
EMAIL_HOST=smtp.gmail.com
EMAIL_PORT=465
EMAIL_USER=your_email
EMAIL_PASS=your_email_app_password
```

Important: do not commit real secrets to the repository.

## Documentation

Project diagrams and analysis files are available in the `docs` directory:

- `docs/architecture-system.puml`
- `docs/architecture.puml`
- `docs/class-diagram.puml`
- `docs/sequence-usecases.puml`
- `docs/ChucNangHeThong.md`

## API Areas

The backend exposes grouped routes under `/api/v1`, including:

- `/auth`
- `/exams`
- `/attempts`
- `/dashboard`
- `/ai`
- `/users`
- `/channels`
- `/subscriptions`
- `/notifications`
- `/admin`
- `/reports`

## Development Notes

- Frontend uses path alias `@` mapped to `quiz-react/src`
- Vite dev server runs on port `5173`
- Express server runs on port `5000` by default
- Static uploads are served from `/uploads`

## Status

T-Edu is structured as a full-stack learning platform with student, creator, and admin flows already present in the codebase. The repository is a solid base for continued feature development, polishing, deployment, and documentation improvements.
