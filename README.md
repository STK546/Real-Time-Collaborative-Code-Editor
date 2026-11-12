# Real-Time Collaborative Code Editor

A full-stack collaborative coding workspace with real-time editing, AI assistance, and integrated terminal.

## Features

- **Real-time collaboration** — Live code editing with Socket.IO, cursor presence, and active user panel
- **Monaco Editor** — VS Code-like editor with tabs, syntax highlighting, and dirty state tracking
- **File management** — Nested file/folder tree with create, rename, drag-and-drop, and file locking
- **Project chat** — Persistent chat with emoji reactions and Ably realtime support
- **AI assistant** — Explain, fix, refactor, and generate code via Groq; natural-language file commands via AI Console
- **Terminal & code execution** — Run Python, JavaScript, shell, PHP locally; C, C++, Java, Go, Rust, and more via Judge0
- **HTML preview** — Live iframe preview for HTML/CSS files
- **Revision history** — File snapshots for every save and autosave
- **Auth & roles** — JWT-based auth with owner/editor/viewer role-based access

## Tech Stack

**Frontend** — React 18, TypeScript, Vite, Monaco Editor, Tailwind CSS, shadcn/ui, Zustand, Socket.IO client

**Backend** — Node.js, Express, MongoDB (Mongoose), Socket.IO, JWT, Groq API, Judge0 API, Ably

## Getting Started

### 1. Install dependencies

```bash
# Frontend
npm install

# Backend
npm install --prefix server
```

### 2. Configure environment

Create a `server/.env` file:

```env
PORT=5000
MONGODB_URI=mongodb://127.0.0.1:27017/code_together
JWT_SECRET=your_secret_here
CLIENT_URL=http://localhost:8080
GROQ_API_KEY=your_groq_key         # Required for AI features
ABLY_API_KEY=your_ably_server_key  # Optional, chat falls back to polling
```

Create a root `.env` file:

```env
VITE_API_URL=http://localhost:5000/api
VITE_ABLY_API_KEY=your_ably_browser_key  # Optional
```

### 3. Run locally

```bash
# Terminal 1 — Backend
npm run dev:server

# Terminal 2 — Frontend
npm run dev:client
```

- Frontend: `http://localhost:8080`
- Backend: `http://localhost:5000`

## Deployment

The frontend is configured for Vercel (`vercel.json` included). The backend needs separate hosting with MongoDB, JWT, Groq, and optional Ably configured via environment variables.

## License

No license file is currently included.
