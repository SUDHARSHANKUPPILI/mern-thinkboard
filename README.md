# 🧠 ThinkBoard — Full-Stack MERN Notes Application

<div align="center">

![ThinkBoard Banner](https://img.shields.io/badge/ThinkBoard-MERN%20Notes%20App-6366f1?style=for-the-badge&logo=react&logoColor=white)

[![React](https://img.shields.io/badge/React-19.x-61DAFB?style=flat-square&logo=react&logoColor=black)](https://react.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=flat-square&logo=node.js&logoColor=white)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express.js-5.x-000000?style=flat-square&logo=express&logoColor=white)](https://expressjs.com/)
[![MongoDB](https://img.shields.io/badge/MongoDB-Atlas-47A248?style=flat-square&logo=mongodb&logoColor=white)](https://www.mongodb.com/atlas)
[![Vite](https://img.shields.io/badge/Vite-6.x-646CFF?style=flat-square&logo=vite&logoColor=white)](https://vitejs.dev/)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-4.x-06B6D4?style=flat-square&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Upstash](https://img.shields.io/badge/Upstash-Redis-00E9A3?style=flat-square&logo=upstash&logoColor=white)](https://upstash.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

**A production-ready, full-stack note-taking application built with the MERN stack — featuring Redis-backed rate limiting, client-side routing, and a responsive UI.**

[🚀 Live Demo](#) · [🐛 Report Bug](https://github.com/SUDHARSHANKUPPILI/mern-thinkboard/issues) · [💡 Request Feature](https://github.com/SUDHARSHANKUPPILI/mern-thinkboard/issues)

</div>

---

## 📋 Table of Contents

- [📖 About](#-about)
- [⚡ Key Highlights](#-key-highlights)
- [📊 Project Statistics](#-project-statistics)
- [✨ Features](#-features)
- [🛠️ Tech Stack](#️-tech-stack)
- [🏗️ Architecture](#️-architecture)
- [📁 Folder Structure](#-folder-structure)
- [🖼️ Screenshots](#️-screenshots)
- [⚙️ Installation](#️-installation)
- [🔐 Environment Variables](#-environment-variables)
- [▶️ Running Locally](#️-running-locally)
- [🌐 API Endpoints](#-api-endpoints)
- [🚀 Deployment Guide](#-deployment-guide)
- [💡 Challenges Faced](#-challenges-faced)
- [🔮 Future Roadmap](#-future-roadmap)
- [🎓 Learning Outcomes](#-learning-outcomes)
- [🙏 Acknowledgements](#-acknowledgements)
- [📄 License](#-license)

---

## 📖 About

**ThinkBoard** is a full-stack MERN notes application for creating, reading, updating, and deleting personal notes through a clean, responsive interface.

The backend is an Express REST API backed by MongoDB Atlas, with every request gated behind Upstash Redis rate limiting. The frontend is a React 19 SPA bootstrapped with Vite, using React Router v7 for client-side navigation. In production, Express serves the Vite build statically — a single deployable Node.js service with no separate frontend server.

> Built as a portfolio project to demonstrate end-to-end full-stack JavaScript development, REST API design, and production-minded architecture.

---

## ⚡ Key Highlights

- 🏎️ **Single deployment unit** — Express serves the Vite build in production; no separate frontend server or CORS required
- 🔒 **Redis-backed rate limiting** — Upstash Redis middleware enforces request thresholds and returns a meaningful 429 UI
- ⚡ **Vite + React 19** — Sub-second HMR in development with an optimized production bundle
- 🗺️ **Dynamic client-side routing** — `/notes/:id` routes via React Router v7 with no full-page reloads
- 🔔 **Instant feedback** — Toast notifications for every CRUD operation via `react-hot-toast`
- 📱 **Fully responsive** — Tailwind CSS 4.x grid layout adapts seamlessly across all screen sizes

---

## 📊 Project Statistics

| Metric | Value |
|---|---|
| React Components | 7 (Navbar, NoteCard, HomePage, CreatePage, NoteDetailPage, NotesNotFound, RateLimitedUI) |
| API Endpoints | 5 (GET all, GET by ID, POST, PUT, DELETE) |
| Custom Middleware | 1 (Redis rate limiter) |
| Environment Variables | 4 (PORT, NODE_ENV, MONGO_URI, Upstash credentials) |
| Database | MongoDB Atlas (cloud-hosted NoSQL) |
| Deployment Target | Render / Railway (single Node.js service) |

---

## ✨ Features

- **Create & Edit Notes** — Title + content form with character counter; inline editing on the detail page
- **Note Grid** — Responsive card layout sorted newest-first with formatted creation dates
- **Delete Notes** — Available from both the home grid and the note detail page
- **Rate Limiting** — API throttled via Upstash Redis; dedicated 429 UI with countdown timer
- **Toast Notifications** — Success and error feedback via `react-hot-toast`
- **Environment-aware API URL** — Axios instance switches between `localhost:5001` (dev) and `/api` (production) at runtime
- **Dot-grid Background** — Global CSS decorative pattern for a polished aesthetic
- **Responsive Design** — Fully adaptive layout via Tailwind CSS 4.x

---

## 🛠️ Tech Stack

### Frontend
| Technology | Version | Purpose |
|---|---|---|
| [React](https://react.dev/) | 19.x | UI library |
| [React Router](https://reactrouter.com/) | 7.x | Client-side routing |
| [Vite](https://vitejs.dev/) | 6.x | Build tool & dev server |
| [Tailwind CSS](https://tailwindcss.com/) | 4.x | Utility-first CSS styling |
| [Axios](https://axios-http.com/) | 1.x | HTTP client for API requests |
| [Lucide React](https://lucide.dev/) | 0.563.x | Icon library |
| [react-hot-toast](https://react-hot-toast.com/) | 2.x | Toast notification system |

### Backend
| Technology | Version | Purpose |
|---|---|---|
| [Node.js](https://nodejs.org/) | 18+ | JavaScript runtime |
| [Express.js](https://expressjs.com/) | 5.x | HTTP server & REST API framework |
| [Mongoose](https://mongoosejs.com/) | 8.x | MongoDB ODM |
| [dotenv](https://www.npmjs.com/package/dotenv) | 16.x | Environment variable management |
| [cors](https://www.npmjs.com/package/cors) | 2.x | Cross-Origin Resource Sharing (dev only) |
| [nodemon](https://nodemon.io/) | 3.x | Development auto-restart |

### Database & Infrastructure
| Technology | Purpose |
|---|---|
| [MongoDB Atlas](https://www.mongodb.com/atlas) | Cloud-hosted NoSQL database |
| [Upstash Redis](https://upstash.com/) | Serverless Redis for API rate limiting |

---

## 🏗️ Architecture

ThinkBoard follows a standard three-tier MERN architecture:

```
┌─────────────────────┐       REST API        ┌──────────────────────────┐
│                     │  (/api/notes, CRUD)   │                          │
│   React Frontend    │ ─────────────────────▶│   Express.js Backend     │
│   (Vite, Port 5173) │                       │   (Node.js, Port 5001)   │
│                     │ ◀─────────────────────│                          │
└─────────────────────┘    JSON Responses     └──────────┬───────────────┘
                                                         │
                                              ┌──────────▼───────────────┐
                                              │                          │
                                              │    MongoDB Atlas         │
                                              │  (Cloud NoSQL Database)  │
                                              │                          │
                                              └──────────────────────────┘
                                                         │
                                              ┌──────────▼───────────────┐
                                              │                          │
                                              │   Upstash Redis          │
                                              │  (Rate Limiter Middleware)│
                                              │                          │
                                              └──────────────────────────┘
```

**Request lifecycle:**

1. **React SPA** sends HTTP requests via Axios to the Express REST API
2. Every request passes through the `rateLimiter` middleware — exceeding the threshold returns `429 Too Many Requests` immediately
3. Valid requests reach the controller layer, performing CRUD on MongoDB Atlas via Mongoose
4. **In production**, Express serves the Vite-built static files directly — single origin, no CORS, no separate frontend server

---

## 📁 Folder Structure

```
mern-thinkboard/
├── package.json                  # Root scripts (build, start)
│
├── backend/
│   ├── package.json
│   ├── .env                      # Not committed
│   └── src/
│       ├── Server.js             # Express entry point & middleware setup
│       ├── config/
│       │   ├── db.js             # MongoDB connection via Mongoose
│       │   └── upstash.js        # Upstash Redis & Ratelimit configuration
│       ├── controllers/
│       │   └── notesController.js# getAllNotes, getNoteById, createNote, updateNote, deleteNote
│       ├── middleware/
│       │   └── rateLimiter.js    # Global rate limiting middleware
│       ├── models/
│       │   └── Note.js           # Mongoose schema & model
│       └── routes/
│           └── notesRoutes.js    # Express router mapping HTTP verbs to controllers
│
└── frontend/
    ├── package.json
    ├── index.html
    ├── vite.config.js
    ├── tailwind.config.js
    └── src/
        ├── main.jsx              # React bootstrap (BrowserRouter)
        ├── App.jsx               # Root component & route definitions
        ├── index.css             # Global styles
        ├── lib/
        │   ├── axios.js          # Configured Axios instance (env-aware base URL)
        │   └── utils.js          # Utility helpers (date formatting)
        ├── components/
        │   ├── Navbar.jsx
        │   ├── NoteCard.jsx
        │   ├── NotesNotFound.jsx
        │   └── RateLimitedUI.jsx # UI shown when rate limit is hit (429)
        └── pages/
            ├── HomePage.jsx
            ├── CreatePage.jsx
            └── NoteDetailPage.jsx
```

---

## 🖼️ Screenshots

| Page | Screenshot |
|---|---|
| 🏠 Home Page (Note Grid) | ![Home Page](screenshots/home-page.png) |
| ➕ Create Note Page | ![Create Note Page](screenshots/create-note-page.png) |
| 🔍 Note Detail / Edit Page | ![Edit Note Page](screenshots/edit-note-page.png) |
| 🚦 Rate Limit UI (429) | ![Rate Limit UI](screenshots/rate-limit-ui.png) |

---

## ⚙️ Installation

### Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [npm](https://www.npmjs.com/) v9+
- A [MongoDB Atlas](https://www.mongodb.com/atlas) cluster
- An [Upstash](https://upstash.com/) Redis database

### Clone the Repository

```bash
git clone https://github.com/SUDHARSHANKUPPILI/mern-thinkboard.git
cd mern-thinkboard
```

### Install Dependencies

```bash
# Backend
cd backend && npm install

# Frontend
cd ../frontend && npm install
```

Or use the root script to install everything and build the frontend in one step:

```bash
npm run build
```

---

## 🔐 Environment Variables

Create `backend/.env`:

```env
# Server
PORT=5001
NODE_ENV=development

# MongoDB
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/<dbname>?retryWrites=true&w=majority

# Upstash Redis (Rate Limiting)
UPSTASH_REDIS_REST_URL=https://xxxx.upstash.io
UPSTASH_REDIS_REST_TOKEN=your_upstash_redis_rest_token
```

> ⚠️ **Never commit `.env`.** It is already listed in `.gitignore`.

| Variable | Where to get it |
|---|---|
| `MONGO_URI` | [MongoDB Atlas](https://cloud.mongodb.com/) → Connect → Drivers |
| `UPSTASH_REDIS_REST_URL` / `TOKEN` | [Upstash Console](https://console.upstash.com/) → Redis DB → REST API |

---

## ▶️ Running Locally

**Terminal 1 — Backend:**

```bash
cd backend
npm run dev
# API server at http://localhost:5001
```

**Terminal 2 — Frontend:**

```bash
cd frontend
npm run dev
# React app at http://localhost:5173
```

> The Vite dev server proxies `/api` requests to `http://localhost:5001` automatically via the Axios base URL config.

---

## 🌐 API Endpoints

All routes are prefixed with `/api` and protected by the rate limiter middleware.

| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|--------------|
| `GET` | `/api/notes` | All notes, sorted newest first | — |
| `GET` | `/api/notes/:id` | Single note by MongoDB `_id` | — |
| `POST` | `/api/notes` | Create a note | `{ "title": "string", "content": "string" }` |
| `PUT` | `/api/notes/:id` | Update a note | `{ "title": "string", "content": "string" }` |
| `DELETE` | `/api/notes/:id` | Delete a note | — |

**Rate limit exceeded:**

```json
HTTP 429 Too Many Requests
{ "message": "Too many requests, please try again later." }
```

**Note schema:**

```json
{
  "_id": "ObjectId (auto-generated)",
  "title": "String (required)",
  "content": "String (required)",
  "createdAt": "Date (auto-generated)",
  "updatedAt": "Date (auto-generated)"
}
```

---

## 🚀 Deployment Guide

### Option 1 — Render *(Recommended)*

1. Push to GitHub and connect your repo at [Render.com](https://render.com/)
2. **Build Command:** `npm run build`
3. **Start Command:** `npm start`
4. Add all `.env` variables in the Render dashboard
5. Deploy — Express serves the Vite build at the same origin

> `NODE_ENV=production` disables CORS and enables static file serving from `frontend/dist/`.

### Option 2 — Railway

```bash
npm install -g @railway/cli
railway login && railway init
railway variables set KEY=VALUE
railway up
```

### Option 3 — Split Deployment

- **Frontend** → [Vercel](https://vercel.com/) or [Netlify](https://www.netlify.com/) (`frontend/dist/`)
- **Backend** → [Render](https://render.com/), [Railway](https://railway.app/), or [Fly.io](https://fly.io/)

---

## 💡 Challenges Faced

- **Rate Limit UX** — Designing a helpful 429 experience (countdown timer, retry CTA) that keeps users informed without causing confusion required iterating on the `RateLimitedUI` component carefully
- **Dynamic API Base URL** — Switching between `localhost:5001` (dev) and `/api` (production) without environment-specific builds required a shared Axios instance with runtime detection
- **Production Static Serving** — Configuring Express to resolve the Vite build path (`frontend/dist/`) correctly across deployment environments required careful use of `path.resolve` and `__dirname`
- **Environment Parity** — Ensuring behaviour is consistent between local dev and cloud deployment (Atlas connection strings, Redis credentials, CORS flags) needed thorough `.env` management

---

## 🔮 Future Roadmap

- [ ] **User Authentication** — JWT-based login/register with `bcryptjs` + `jsonwebtoken`
- [ ] **Search & Filter** — Real-time search by title or content on the home page
- [ ] **Note Categories / Tags** — Tag notes and filter by category
- [ ] **Markdown Support** — Render note content as Markdown via `react-markdown`
- [ ] **Pagination** — Cursor-based or offset pagination for large note collections
- [ ] **Dark / Light Mode** — User-controlled theme toggle
- [ ] **Rich Text Editor** — Replace plain textarea with `Tiptap` or `Quill.js`
- [ ] **Testing** — Backend: Jest + Supertest; Frontend: Vitest + React Testing Library
- [ ] **CI/CD Pipeline** — GitHub Actions for lint, test, and auto-deploy on push
- [ ] **Note Pinning** — Pin important notes to the top of the grid

---

## 🎓 Learning Outcomes

Building ThinkBoard provided hands-on experience across the entire JavaScript stack:

| Area | What I Practised |
|---|---|
| REST API Design | CRUD routes, HTTP verbs, status codes, structured JSON responses |
| MongoDB & Mongoose | Schema definition, Atlas connection, async CRUD operations |
| React Hooks | `useState`, `useEffect`, `useParams` for state and side effects |
| React Router v7 | Dynamic routes, `<Link>`, programmatic navigation |
| Axios | Shared instance with environment-aware base URL |
| Rate Limiting | Custom Express middleware integrating a serverless Redis service |
| Environment Config | `.env`, `dotenv`, multi-environment variable management |
| Production Build | Express serving Vite static output; monorepo-style root scripts |
| Error Handling | Toast notifications, loading states, meaningful 429 UX |
| Full-Stack Integration | Connecting a React SPA to a Node/Express API end-to-end |

---

## 🙏 Acknowledgements

- Inspired by a full-stack MERN tutorial; extended with additional features, UI polish, and production-minded improvements
- README and code assisted by **[Claude Code](https://claude.ai/)**, **[Antigravity AI](https://antigravity.dev/)**, and **[ChatGPT](https://chat.openai.com/)**
- Icons by [Lucide](https://lucide.dev/)
- Hosting infrastructure by [Render](https://render.com/) and [Upstash](https://upstash.com/)

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for details.

---

<div align="center">

**Sudharshan Kuppili**

[![GitHub](https://img.shields.io/badge/GitHub-SUDHARSHANKUPPILI-181717?style=flat-square&logo=github)](https://github.com/SUDHARSHANKUPPILI)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat-square&logo=linkedin)](https://linkedin.com/in/sudharshankuppili)

⭐ If you found this project useful, a star on [GitHub](https://github.com/SUDHARSHANKUPPILI/mern-thinkboard) would be appreciated!

</div>
