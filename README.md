# MindCare AI (Production Ready)

## What you have
- `client/`: Vite + React frontend
- `server/`: Node + Express API (also serves the built frontend in production)

## Production (single deploy)

### 1) Create environment variables
Create `server/.env` (or set these in your hosting provider). You can copy from `server/.env.example`.

Minimum required:
- `JWT_SECRET`
- `MONGO_URI` (required when `NODE_ENV=production` and `SKIP_DB=false`)

### 2) Install + build
From the project root:

```bash
npm run install:all
npm run build
```

### 3) Start
From the project root:

```bash
npm run start
```

Open:
- App: `http://localhost:5000`
- API health: `http://localhost:5000/api/health`

## Development
In two terminals:

```bash
npm --prefix server run dev
```

```bash
npm --prefix client run dev
```

## Notes (important)
- **Admin endpoints are protected by default.** To disable auth locally only: set `ADMIN_AUTH_DISABLED=true` in `server/.env`.
- **Anonymous privacy**: the frontend sends `X-Session-Id` automatically so anonymous chats/moods/reminders don’t get mixed across users.
- **CORS**: if you deploy frontend + backend on the same domain, you usually don’t need CORS. If you host them separately, set `CORS_ORIGIN` (comma-separated).

# My Fullstack Project

A basic full-stack project structure with a Node.js/Express backend and a React frontend.

## Structure
- `/client`: Frontend (React / Vite)
- `/server`: Backend (Node.js / Express)

## Getting Started
1. Install root dependencies: `npm install`
2. Setup Backend: `cd server && npm install`
3. Setup Frontend: `cd client && npm install`
