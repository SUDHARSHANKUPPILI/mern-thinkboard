# ðŸ§  ThinkBoard â€” A Full-Stack MERN Notes Application

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

**A clean, full-stack note-taking application built with the MERN stack, featuring real-time CRUD operations, intelligent rate limiting, and a responsive UI.**

[ðŸš€ Live Demo](#) Â· [ðŸ› Report Bug](https://github.com/SUDHARSHANKUPPILI/mern-thinkboard/issues) Â· [ðŸ’¡ Request Feature](https://github.com/SUDHARSHANKUPPILI/mern-thinkboard/issues)

</div>

---

## ðŸ“‹ Table of Contents

- [ðŸ“– About the Project](#-about-the-project)
- [âœ¨ Features](#-features)
- [ðŸ› ï¸ Tech Stack](#ï¸-tech-stack)
- [ðŸ—ï¸ Architecture](#ï¸-architecture)
- [ðŸ“ Folder Structure](#-folder-structure)
- [ðŸ–¼ï¸ Screenshots](#ï¸-screenshots)
- [âš™ï¸ Installation](#ï¸-installation)
- [ðŸ” Environment Variables](#-environment-variables)
- [â–¶ï¸ Running Locally](#ï¸-running-locally)
- [ðŸŒ API Endpoints](#-api-endpoints)
- [ðŸš€ Deployment Guide](#-deployment-guide)
- [ðŸ”® Future Improvements](#-future-improvements)
- [ðŸŽ“ Learning Outcomes](#-learning-outcomes)
- [ðŸ“„ License](#-license)

---

## ðŸ“– About the Project

**ThinkBoard** is a full-stack notes management application built using the **MERN stack** (MongoDB, Express.js, React, Node.js). It allows users to create, view, edit, and delete personal notes through a clean and responsive interface.

The project demonstrates a complete end-to-end web application â€” from a RESTful API backend with MongoDB persistence, to a React SPA frontend with client-side routing. It also integrates **Upstash Redis-based rate limiting** to prevent API abuse, making it production-ready in design.

> Built as a portfolio project to showcase full-stack JavaScript development, REST API design, and modern React patterns.

---

## âœ¨ Features

- ðŸ“ **Create Notes** â€” Add new notes with a title and content via a dedicated form page
- ðŸ“‹ **View All Notes** â€” Browse all notes in a responsive card grid layout on the home page
- ðŸ” **View Note Detail** â€” Click any note to navigate to its full detail and editing view
- âœï¸ **Edit Notes** â€” Update the title and content of an existing note inline
- ðŸ—‘ï¸ **Delete Notes** â€” Remove notes with a confirmation prompt (supported on both the home grid and detail page)
- ðŸš¦ **Rate Limiting** â€” API requests are rate-limited via Upstash Redis to prevent abuse; a dedicated UI component informs users when the limit is reached
- ðŸ“… **Date Formatting** â€” Notes display a human-readable formatted creation date
- ðŸ”” **Toast Notifications** â€” Success and error feedback is surfaced through `react-hot-toast` notifications
- ðŸŒ **Dynamic API Base URL** â€” Axios instance auto-switches between development (`localhost:5001`) and production (`/api`) endpoints
- ðŸ“± **Responsive Design** â€” Built with Tailwind CSS for a fully responsive layout across all screen sizes
- ðŸŽ¨ **Decorative Background** â€” Dot-grid CSS background pattern applied globally for a polished aesthetic
- ðŸ”’ **Production CORS** â€” CORS is only enabled in development mode; in production, the Express server serves the built React frontend statically

---

## ðŸ› ï¸ Tech Stack

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
| [cors](https://www.npmjs.com/package/cors) | 2.x | Cross-Origin Resource Sharing |
| [nodemon](https://nodemon.io/) | 3.x | Development auto-restart |

### Database & Infrastructure
| Technology | Purpose |
|---|---|
| [MongoDB Atlas](https://www.mongodb.com/atlas) | Cloud-hosted NoSQL database |
| [Upstash Redis](https://upstash.com/) | Serverless Redis for API rate limiting |

---

## ðŸ—ï¸ Architecture

ThinkBoard follows a standard **three-tier MERN architecture**:

```
â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”       REST API        â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
â”‚                     â”‚  (/api/notes, CRUD)   â”‚                          â”‚
â”‚   React Frontend    â”‚ â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â–¶â”‚   Express.js Backend     â”‚
â”‚   (Vite, Port 5173) â”‚                       â”‚   (Node.js, Port 5001)   â”‚
â”‚                     â”‚ â—€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”‚                          â”‚
â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜    JSON Responses     â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”¬â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
                                                         â”‚
                                              â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
                                              â”‚                          â”‚
                                              â”‚    MongoDB Atlas         â”‚
                                              â”‚  (Cloud NoSQL Database)  â”‚
                                              â”‚                          â”‚
                                              â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
                                                         â”‚
                                              â”Œâ”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â–¼â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”
                                              â”‚                          â”‚
                                              â”‚   Upstash Redis          â”‚
                                              â”‚  (Rate Limiter Middleware)â”‚
                                              â”‚                          â”‚
                                              â””â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”˜
```

**How it works:**

1. **Client (React SPA):** The user interacts with the React app served by Vite. Pages are routed client-side via React Router v7. Axios sends HTTP requests to the backend REST API.

2. **Backend (Express API):** The Express server exposes a RESTful API under `/api/notes`. Before processing any request, a custom `rateLimiter` middleware checks against Upstash Redis. If the limit is exceeded, a `429 Too Many Requests` response is returned immediately.

3. **Database (MongoDB Atlas):** Notes are stored as documents in a MongoDB Atlas cloud database. Mongoose provides the ODM layer with schema validation.

4. **Production Mode:** In production, Express serves the Vite-built React static files and proxies all `/api` routes, eliminating the need for a separate frontend server. CORS middleware is disabled in production.

---

## ðŸ“ Folder Structure

```
mern-thinkboard/
â”œâ”€â”€ package.json                  # Root-level scripts (build, start)
â”‚
â”œâ”€â”€ backend/
â”‚   â”œâ”€â”€ package.json              # Backend dependencies
â”‚   â”œâ”€â”€ .env                      # Environment variables (not committed)
â”‚   â””â”€â”€ src/
â”‚       â”œâ”€â”€ Server.js             # Express app entry point, middleware setup
â”‚       â”œâ”€â”€ config/
â”‚       â”‚   â”œâ”€â”€ db.js             # MongoDB connection via Mongoose
â”‚       â”‚   â””â”€â”€ upstash.js        # Upstash Redis & Ratelimit configuration
â”‚       â”œâ”€â”€ controllers/
â”‚       â”‚   â””â”€â”€ notesController.js# CRUD logic: getAllNotes, getNoteById,
â”‚       â”‚                         #             createNote, updateNote, deleteNote
â”‚       â”œâ”€â”€ middleware/
â”‚       â”‚   â””â”€â”€ rateLimiter.js    # Global rate limiting middleware
â”‚       â”œâ”€â”€ models/
â”‚       â”‚   â””â”€â”€ Note.js           # Mongoose schema & model for a Note
â”‚       â””â”€â”€ routes/
â”‚           â””â”€â”€ notesRoutes.js    # Express router: maps HTTP verbs to controllers
â”‚
â””â”€â”€ frontend/
    â”œâ”€â”€ package.json              # Frontend dependencies
    â”œâ”€â”€ index.html                # HTML entry point
    â”œâ”€â”€ vite.config.js            # Vite configuration
    â”œâ”€â”€ tailwind.config.js        # Tailwind CSS configuration
    â””â”€â”€ src/
        â”œâ”€â”€ main.jsx              # React app bootstrap (BrowserRouter)
        â”œâ”€â”€ App.jsx               # Root component with route definitions
        â”œâ”€â”€ index.css             # Global styles
        â”œâ”€â”€ lib/
        â”‚   â”œâ”€â”€ axios.js          # Configured Axios instance (dynamic base URL)
        â”‚   â””â”€â”€ utils.js          # Utility helpers (e.g., date formatting)
        â”œâ”€â”€ components/
        â”‚   â”œâ”€â”€ Navbar.jsx        # Top navigation bar
        â”‚   â”œâ”€â”€ NoteCard.jsx      # Card component for note preview with delete
        â”‚   â”œâ”€â”€ NotesNotFound.jsx # Empty state UI when no notes exist
        â”‚   â””â”€â”€ RateLimitedUI.jsx # UI displayed when rate limit is hit (429)
        â””â”€â”€ pages/
            â”œâ”€â”€ HomePage.jsx      # Fetches & displays all notes in a grid
            â”œâ”€â”€ CreatePage.jsx    # Form to create a new note
            â””â”€â”€ NoteDetailPage.jsx# Fetches, displays, edits & deletes a single note
```

---

## ðŸ–¼ï¸ Screenshots

| Page | Screenshot |
|---|---|
| ðŸ  Home Page (Note Grid) | `[Add screenshot here]` |
| âž• Create Note Page | `[Add screenshot here]` |
| ðŸ” Note Detail / Edit Page | `[Add screenshot here]` |
| ðŸš¦ Rate Limit UI (429) | `[Add screenshot here]` |

---

## âš™ï¸ Installation

### Prerequisites

Ensure the following are installed on your system:

- [Node.js](https://nodejs.org/) **v18 or later**
- [npm](https://www.npmjs.com/) **v9 or later**
- A [MongoDB Atlas](https://www.mongodb.com/atlas) account and cluster
- An [Upstash](https://upstash.com/) account with a Redis database

### Clone the Repository

```bash
git clone https://github.com/SUDHARSHANKUPPILI/mern-thinkboard.git
cd mern-thinkboard
```

### Install Dependencies

Install backend and frontend dependencies separately:

```bash
# Install backend dependencies
cd backend
npm install

# Install frontend dependencies
cd ../frontend
npm install
```

Alternatively, from the root directory:

```bash
npm run build
```
> This root-level script installs all dependencies and builds the frontend in one step.

---

## ðŸ” Environment Variables

Create a `.env` file inside the `backend/` directory with the following variables:

```env
# â”€â”€ Server â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€
PORT=5001
NODE_ENV=development

# â”€â”€ MongoDB â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€
MONGO_URI=mongodb+srv://<username>:<password>@cluster0.xxxxx.mongodb.net/<dbname>?retryWrites=true&w=majority

# â”€â”€ Upstash Redis (Rate Limiting) â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€â”€
UPSTASH_REDIS_REST_URL=https://xxxx.upstash.io
UPSTASH_REDIS_REST_TOKEN=your_upstash_redis_rest_token
```

> âš ï¸ **Never commit your `.env` file.** It is already listed in `.gitignore`.

#### Where to get these values:
- **MONGO_URI** â†’ [MongoDB Atlas](https://cloud.mongodb.com/) â†’ Your Cluster â†’ Connect â†’ Drivers
- **UPSTASH_REDIS_REST_URL / TOKEN** â†’ [Upstash Console](https://console.upstash.com/) â†’ Your Redis Database â†’ REST API

---

## â–¶ï¸ Running Locally

Run the backend and frontend in **separate terminal windows**:

**Terminal 1 â€” Backend:**

```bash
cd backend
npm run dev
```

The API server will start at: `http://localhost:5001`

**Terminal 2 â€” Frontend:**

```bash
cd frontend
npm run dev
```

The React application will open at: `http://localhost:5173`

> The Vite dev server proxies API requests to `http://localhost:5001/api` automatically via the dynamic Axios base URL.

---

## ðŸŒ API Endpoints

All routes are prefixed with `/api`.

| Method | Endpoint | Description | Request Body |
|--------|----------|-------------|--------------|
| `GET` | `/api/notes` | Retrieve all notes, sorted newest first | â€” |
| `GET` | `/api/notes/:id` | Retrieve a single note by its MongoDB `_id` | â€” |
| `POST` | `/api/notes` | Create a new note | `{ "title": "string", "content": "string" }` |
| `PUT` | `/api/notes/:id` | Update an existing note by `_id` | `{ "title": "string", "content": "string" }` |
| `DELETE` | `/api/notes/:id` | Delete a note by its `_id` | â€” |

### Rate Limiting

All routes are protected by the **Upstash Redis rate limiter** middleware. Exceeding the configured threshold will result in:

```json
HTTP 429 Too Many Requests
{
  "message": "Too many requests, please try again later."
}
```

### Note Schema

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

## ðŸš€ Deployment Guide

### Option 1 â€” Render (Recommended for Full-Stack)

1. Push your code to GitHub.
2. Go to [Render.com](https://render.com/) and create a new **Web Service**.
3. Connect your GitHub repository.
4. Set the **Build Command**: `npm run build`
5. Set the **Start Command**: `npm start`
6. Add all environment variables from your `.env` file in the Render dashboard.
7. Deploy.

> In production mode, `NODE_ENV=production` disables CORS, and Express serves the Vite build from `frontend/dist/` directly.

### Option 2 â€” Railway

1. Install the Railway CLI: `npm install -g @railway/cli`
2. Run `railway login` and `railway init`
3. Set environment variables via `railway variables set KEY=VALUE`
4. Deploy with `railway up`

### Option 3 â€” Separate Deployment

- **Frontend**: Deploy `frontend/dist/` to [Vercel](https://vercel.com/) or [Netlify](https://www.netlify.com/). Set the `VITE_API_BASE_URL` if required.
- **Backend**: Deploy to [Render](https://render.com/), [Railway](https://railway.app/), or [Fly.io](https://fly.io/).

---

## ðŸ”® Future Improvements

The following enhancements are planned or suggested for future iterations:

- [ ] **User Authentication** â€” Add JWT-based login and registration so notes are user-specific (using `bcryptjs` + `jsonwebtoken`)
- [ ] **Search & Filter** â€” Add a search bar on the home page to filter notes by title or content in real time
- [ ] **Note Categories / Tags** â€” Allow users to tag notes and filter by category
- [ ] **Markdown Support** â€” Render note content as Markdown using a library like `react-markdown`
- [ ] **Pagination or Infinite Scroll** â€” Implement pagination for users with a large number of notes
- [ ] **Unit & Integration Tests** â€” Add backend tests using Jest + Supertest and frontend tests using Vitest + React Testing Library
- [ ] **Dark / Light Mode Toggle** â€” Add a user-controlled theme switcher
- [ ] **Note Pinning** â€” Allow users to pin important notes to the top of the list
- [ ] **Rich Text Editor** â€” Replace the plain textarea with a rich text editor (e.g., `Quill.js` or `TipTap`)
- [ ] **CI/CD Pipeline** â€” Set up GitHub Actions for automated linting, testing, and deployment on push

---

## ðŸŽ“ Learning Outcomes

Building ThinkBoard reinforced and demonstrated the following skills:

- **REST API Design** â€” Designing and implementing a clean CRUD API following REST conventions using Express.js
- **MongoDB & Mongoose** â€” Defining Mongoose schemas, connecting to MongoDB Atlas, and performing async database operations
- **React with Hooks** â€” Using `useState`, `useEffect`, and `useParams` to manage component state and side effects
- **React Router v7** â€” Implementing client-side routing with dynamic route parameters (`/notes/:id`)
- **Axios HTTP Client** â€” Configuring a shared Axios instance with environment-aware base URLs
- **Rate Limiting** â€” Integrating a third-party serverless Redis service (Upstash) as custom Express middleware
- **Environment Configuration** â€” Managing secrets with `.env` files and `dotenv` for different environments
- **Production Build Flow** â€” Configuring a monorepo-style project where Express serves the Vite production build statically
- **Error Handling & UX** â€” Surfacing API errors and success events through toast notifications and loading states
- **Full-Stack Integration** â€” Connecting a React SPA to a Node/Express backend end-to-end

---

## ðŸ“„ License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for more information.

---

<div align="center">

Made with â¤ï¸ by [Sudharshan Kuppili](https://github.com/SUDHARSHANKUPPILI)

â­ If you found this project helpful, consider giving it a star on [GitHub](https://github.com/SUDHARSHANKUPPILI/mern-thinkboard)!

</div>
