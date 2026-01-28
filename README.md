# 🎨 Excalidraw Clone – Full Stack Collaborative Drawing App

A production-ready, real-time collaborative drawing application inspired by Excalidraw.

This project demonstrates end-to-end system design including frontend, backend APIs, WebSockets, database management, containerization, and cloud deployment.

---

## 🚀 Tech Stack

### Frontend

- Next.js
- React + TypeScript
- Tailwind CSS
- Vercel

### Backend

- Node.js + Express
- WebSocket (ws)
- Prisma ORM
- PostgreSQL
- Render (Docker)

### Tooling

- Turborepo
- pnpm Workspaces
- Docker
- GitHub Actions

---

## 📂 Monorepo Structure

Excalidraw-Clone/
├── apps/
│ ├── web
│ ├── http-backend
│ └── ws-server
├── packages/
│ ├── db
│ ├── backend-common
│ ├── ui
│ └── typescript-config
├── turbo.json
├── package.json
└── pnpm-workspace.yaml

---

## ✨ Features

- Real-time collaboration
- Multi-user rooms
- JWT authentication
- Secure WebSockets
- PostgreSQL persistence
- Automatic migrations
- Dockerized backend

---

## 🛠 Prerequisites

- Node.js >= 18
- pnpm >= 8
- Docker (optional)
- PostgreSQL

---

## ⚙️ Environment Variables

Create `.env` in root.

DATABASE_URL=postgresql://user:password@localhost:5432/excalidraw  
JWT_SECRET=your_secret  
NEXTAUTH_SECRET=your_secret

NEXT_PUBLIC_API_URL=http://localhost:3001  
NEXT_PUBLIC_SOCKET_URL=ws://localhost:4000  
NEXT_PUBLIC_SITE_URL=http://localhost:3000

NODE_ENV=development

Production envs are set in Render/Vercel.

---

## 📦 Installation

git clone https://github.com/your-username/excalidraw-clone.git  
cd excalidraw-clone  
pnpm install

---

## 🗄 Database Setup (Local)

Using Docker:

docker run -d \
 --name excali-db \
 -p 5432:5432 \
 -e POSTGRES_USER=user \
 -e POSTGRES_PASSWORD=password \
 -e POSTGRES_DB=excalidraw \
 postgres:15

Run migrations:

pnpm db:migrate

---

## ▶️ Running Locally

Start everything:

pnpm dev

Services:

Frontend: http://localhost:3000  
Backend: http://localhost:3001  
WebSocket: ws://localhost:4000

---

## Individual Services

pnpm dev:web  
pnpm dev:api  
pnpm dev:ws

---

## 🏗 Build

pnpm build

---

## 🐳 Docker (Production)

docker build -f apps/http-backend/Dockerfile -t excali-backend .

Used for Render deployment.

---

## ☁️ Deployment

### Backend & WS (Render)

- Create Web Service
- Select Docker
- Add env variables
- Enable auto deploy

### Frontend (Vercel)

- Import GitHub repo
- Select apps/web
- Add env variables
- Deploy

---

## 🔄 Database Migrations

Migrations run on startup:

pnpm db:migrate

---

## 🔌 WebSocket Usage

Example:

const ws = new WebSocket(
"wss://your-ws.onrender.com?token=JWT_TOKEN"
);

---

## 🧪 Testing

Manual testing  
Future: Jest, Playwright

---

## 🚦 CI/CD

- GitHub auto deploy
- Render & Vercel pipelines
- Prisma migrations on startup

---

## 📈 Performance

- Stateless services
- Connection pooling
- CDN via Vercel

---

## 🔐 Security

- JWT authentication
- Secure env vars
- CORS
- WSS

---

## 📝 Resume Summary

Built and deployed a real-time collaborative drawing platform using Next.js, Node.js, WebSockets, Prisma, PostgreSQL, Docker, Render, and Vercel in a Turborepo monorepo.

---

## 📌 Future Improvements

- Redis pub/sub
- RBAC
- Offline sync
- Versioning
- Mobile support

---

## 👨‍💻 Author

Rohit Kumar

---

## ⭐ Acknowledgements

Inspired by Excalidraw  
Built for learning and production experimentation
