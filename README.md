# E-TODO — Fullstack Task Manager

> Production-style todo app with secured auth, dockerized backend, and a React frontend with light/dark mode.

[![React](https://img.shields.io/badge/React-18-61DAFB?style=flat&logo=react&logoColor=black)](https://react.dev/)
[![Node.js](https://img.shields.io/badge/Node.js-Express-339933?style=flat&logo=node.js&logoColor=white)](https://nodejs.org/)
[![MySQL](https://img.shields.io/badge/MySQL-database-4479A1?style=flat&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Docker](https://img.shields.io/badge/Docker-containerized-2496ED?style=flat&logo=docker&logoColor=white)](https://www.docker.com/)
[![JWT](https://img.shields.io/badge/Auth-JWT-000000?style=flat&logo=jsonwebtokens&logoColor=white)](https://jwt.io/)

## What it is

E-TODO is a fullstack web app letting users create an account, log in securely, and manage their own task list (CRUD: create / read / update / delete). The backend runs in Docker, the frontend is a React SPA, and authentication uses **JWT with route protection**.

## Stack

### Backend
| Tool          | Purpose                              |
| ------------- | ------------------------------------ |
| Node.js       | Runtime                              |
| Express       | HTTP server + routing                |
| MySQL2        | Database driver                      |
| JWT           | Token-based authentication           |
| bcryptjs      | Password hashing                     |
| Docker        | Containerized backend + database     |

### Frontend
| Tool          | Purpose                  |
| ------------- | ------------------------ |
| React         | UI library               |
| Bootstrap     | Component styling        |
| Vanilla CSS   | Light/dark mode theming  |

## Features

- **User authentication** — register, login, password hashing (bcrypt)
- **JWT session management** — tokens stored client-side, protected routes
- **Task CRUD** — create, list, edit, delete tasks scoped per user
- **Light/Dark mode** — theme toggle persisted in localStorage
- **Fluid React UI** — optimistic updates for snappy UX
- **One-command launch** via Docker Compose

## How it works

```
Frontend (React, :3000)
   │
   │ HTTP + JWT in header
   ▼
Backend (Express, :8080)
   │
   │ SQL (mysql2)
   ▼
MySQL container
```

Authentication flow :
1. User submits credentials → backend hashes the input with bcrypt
2. On match, backend signs a JWT with the user ID
3. Frontend stores the token and attaches it to subsequent requests
4. Protected routes verify the token middleware-side before serving data

## What I learned

- **Authentication done right** — bcrypt salt rounds, JWT signature & expiry, route guards on both sides
- **Docker Compose** — orchestrating backend + database in one `up`, with persistent volumes for MySQL
- **REST API design** — clean endpoints, proper HTTP verbs, status codes that mean something
- **Frontend state management** — handling auth state, optimistic updates, and theme persistence without external state libs
- **Separating concerns** — `backend/` and `frontend/` as independent deployables, communicating only over HTTP

## Project context

- **Year** : 2025–2026
- **School** : Epitech Bachelor, Mulhouse
- **Team** : 2 members (with Zacharie Mando)
- **Course** : Web Development (B-WEB-101)

## Note

This is a portfolio summary. The full source code is private per Epitech academic policy. Available on request for recruiters.

---

[Imran Nogueira](https://github.com/imrannnn30) · MMXXVI
